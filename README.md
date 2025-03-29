<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="refresh" content="0">
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

      // Liens des cartes en fonction des langues
      const carteMidiFr = "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link";  // Carte midi en français
      const carteSoirFr = "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"; // Carte soir en français

      const carteMidiEn = "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link";  // Carte midi en anglais
      const carteSoirEn = "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"; // Carte soir en anglais

      const carteMidiIt = "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link";  // Carte midi en italien
      const carteSoirIt = "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"; // Carte soir en italien

      const carteMidiEs = "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link";  // Carte midi en espagnol
      const carteSoirEs = "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"; // Carte soir en espagnol

      const carteMidiPt = "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link";  // Carte midi en portugais
      const carteSoirPt = "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"; // Carte soir en portugais

      const carteMidiDe = "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link";  // Carte midi en allemand
      const carteSoirDe = "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"; // Carte soir en allemand

      const carteMidiZh = "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link";  // Carte midi en chinois
      const carteSoirZh = "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"; // Carte soir en chinois

      const carteMidiJp = "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link";  // Carte midi en japonais
      const carteSoirJp = "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"; // Carte soir en japonais

      let carteMidi, carteSoir;

      // Vérifier la langue de l'utilisateur et rediriger en fonction
      if (userLang.startsWith("fr")) {
        carteMidi = carteMidiFr;
        carteSoir = carteSoirFr;
      } else if (userLang.startsWith("en")) {
        carteMidi = carteMidiEn;
        carteSoir = carteSoirEn;
      } else if (userLang.startsWith("it")) {
        carteMidi = carteMidiIt;
        carteSoir = carteSoirIt;
      } else if (userLang.startsWith("es")) {
        carteMidi = carteMidiEs;
        carteSoir = carteSoirEs;
      } else if (userLang.startsWith("pt")) {
        carteMidi = carteMidiPt;
        carteSoir = carteSoirPt;
      } else if (userLang.startsWith("de")) {
        carteMidi = carteMidiDe;
        carteSoir = carteSoirDe;
      } else if (userLang.startsWith("zh")) {
        carteMidi = carteMidiZh;
        carteSoir = carteSoirZh;
      } else if (userLang.startsWith("ja")) {
        carteMidi = carteMidiJp;
        carteSoir = carteSoirJp;
      } else {
        // Par défaut, anglais
        carteMidi = carteMidiEn;
        carteSoir = carteSoirEn;
      }

      // Si nous sommes dans la plage horaire du midi (11h30–17h)
      if (totalMinutes >= midiStart && totalMinutes < soirStart) {
        window.location.href = carteMidi;
      } 
      // Si nous sommes dans la plage horaire du soir (17h–22h30)
      else if (totalMinutes >= soirStart && totalMinutes <= soirEnd) {
        window.location.href = carteSoir;
      } 
      // Si c'est en dehors des créneaux (avant 11h30 ou après 22h30)
      else {
        document.getElementById("message").style.display = "block";
      }
    };
  </script>
</head>
<body>
  <div id="message" style="display:none; text-align:center; margin-top: 50px;">
    <h2>Le Caprice Café vous accueille prochainement !</h2>
    <p>Les cartes sont disponibles de 11h30 à 17h (midi) et de 17h à 22h30 (soir).</p>
    <p><a href="https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link">Voir la carte du midi (PDF)</a></p>
    <p><a href="https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link">Voir la carte du soir (PDF)</a></p>
  </div>
</body>
</html>
