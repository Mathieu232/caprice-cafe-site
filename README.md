<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <title>Carte du Caprice Café</title>
  <script>
    window.onload = function () {
      const userLang = navigator.language || navigator.userLanguage; // Détection de la langue du navigateur
      const now = new Date();
      const hour = now.getHours();
      const minutes = now.getMinutes();
      const totalMinutes = hour * 60 + minutes;

      // Créneaux d'affichage : midi (11h30–17h), soir (17h–22h30)
      const midiStart = 11 * 60 + 30;
      const midiEnd = 17 * 60;
      const soirStart = 17 * 60;
      const soirEnd = 22 * 60 + 30;

      // Lien de la carte PDF en français
      const carteFr = "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link"; 

      // Choisir la langue cible pour Google Translate en fonction du navigateur
      let targetLang = 'es'; // Par défaut, espagnol
      if (userLang.startsWith("en")) targetLang = 'en';
      else if (userLang.startsWith("it")) targetLang = 'it';
      else if (userLang.startsWith("de")) targetLang = 'de';

      // Lien de traduction Google
      const translatedLink = `https://translate.google.com/translate?sl=fr&tl=${targetLang}&u=${carteFr}`;

      // Rediriger en fonction de l'heure
      if (totalMinutes >= midiStart && totalMinutes < soirStart) {
        window.location.href = translatedLink; // Redirige vers la carte du midi traduite
      } else if (totalMinutes >= soirStart && totalMinutes <= soirEnd) {
        window.location.href = translatedLink; // Redirige vers la carte du soir traduite
      } else {
        document.getElementById("message").style.display = "block"; // Affiche un message si en dehors des horaires
      }
    };
  </script>
</head>
<body>
  <div id="message" style="display:none; text-align:center; margin-top: 50px;">
    <h2>Le Caprice Café vous accueille prochainement !</h2>
    <p>Les cartes sont disponibles de 11h30 à 17h (midi) et de 17h à 22h30 (soir).</p>
  </div>
</body>
</html>
