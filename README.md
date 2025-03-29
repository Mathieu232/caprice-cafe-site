<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Carte du Caprice Café</title>
  <script>
    window.onload = function () {
      const userLang = navigator.language || navigator.userLanguage; // Détection de la langue du navigateur
      console.log("Langue détectée : " + userLang); // Afficher la langue détectée dans la console (pour tester)

      // Liens des cartes en fonction des langues (les liens doivent être valides)
      const carteMidi = {
        fr: "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link", // Carte midi en français
        en: "https://drive.google.com/file/d/1XXXXXX/view?usp=drive_link", // Carte midi en anglais
        it: "https://drive.google.com/file/d/1ZZZZZZ/view?usp=drive_link", // Carte midi en italien
        es: "https://drive.google.com/file/d/1BBBBBB/view?usp=drive_link", // Carte midi en espagnol
      };

      const carteSoir = {
        fr: "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link", // Carte soir en français
        en: "https://drive.google.com/file/d/1YYYYYY/view?usp=drive_link", // Carte soir en anglais
        it: "https://drive.google.com/file/d/1AAAAAA/view?usp=drive_link", // Carte soir en italien
        es: "https://drive.google.com/file/d/1CCCCC/view?usp=drive_link", // Carte soir en espagnol
      };

      // Choisir la langue du navigateur et afficher la carte correspondante
      let lang = 'fr';  // Valeur par défaut (français)
      if (userLang.startsWith("en")) {
        lang = 'en';
      } else if (userLang.startsWith("it")) {
        lang = 'it';
      } else if (userLang.startsWith("es")) {
        lang = 'es';
      }

      // Rediriger l'utilisateur vers la carte appropriée
      window.location.href = totalMinutes >= midiStart && totalMinutes < soirStart ? carteMidi[lang] : carteSoir[lang];
    };
  </script>
</head>
<body>
  <h1>Le Caprice Café</h1>
  <p>Les cartes sont disponibles de 11h30 à 17h (midi) et de 17h à 22h30 (soir).</p>
  <button onclick="window.location.href='https://translate.google.com'">Traduire cette page</button>  <!-- Ajout d'un bouton de traduction -->
</body>
</html>
