<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="refresh" content="0">
  <title>Carte du Caprice Café</title>
  <script>
    window.onload = function () {
      const userLang = navigator.language || navigator.userLanguage; // Détection de la langue du navigateur
      console.log("Langue détectée : " + userLang); // Afficher la langue détectée dans la console (pour tester)
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
      const cartes = {
        fr: {
          midi: "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link",  // Carte midi en français
          soir: "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"  // Carte soir en français
        },
        en: {
          midi: "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link",  // Carte midi en anglais
          soir: "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"  // Carte soir en anglais
        },
        it: {
          midi: "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link",  // Carte midi en italien
          soir: "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"  // Carte soir en italien
        },
        es: {
          midi: "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link",  // Carte midi en espagnol
          soir: "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"  // Carte soir en espagnol
        },
        pt: {
          midi: "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link",  // Carte midi en portugais
          soir: "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"  // Carte soir en portugais
        },
        de: {
          midi: "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link",  // Carte midi en allemand
          soir: "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"  // Carte soir en allemand
        },
        zh: {
          midi: "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link",  // Carte midi en chinois
          soir: "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"  // Carte soir en chinois
        },
        ja: {
          midi: "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link",  // Carte midi en japonais
          soir: "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link"  // Carte soir en japonais
        }
      };

      let carteMidi, carteSoir;

      // Choisir la langue du navigateur et attribuer les cartes correspondantes
      if (userLang.startsWith("fr")) {
        carteMidi = cartes.fr.midi;
        carteSoir = cartes.fr.soir;
      } else if (userLang.startsWith("en")) {
        carteMidi = cartes.en.midi;
        carteSoir = cartes.en.soir;
      } else if (userLang.startsWith("it")) {
        carteMidi = cartes.it.midi;
        carteSoir = cartes.it.soir;
      } else if (userLang.startsWith("es")) {
        carteMidi = cartes.es.midi;
        carteSoir = cartes.es.soir;
      } else if (userLang.startsWith("pt")) {
        carteMidi = cartes.pt.midi;
        carteSoir = cartes.pt.soir;
      } else if (userLang.startsWith("de")) {
        carteMidi = cartes.de.midi;
        carteSoir = cartes.de.soir;
      } else if (userLang.startsWith("zh")) {
        carteMidi = cartes.zh.midi;
        carteSoir = cartes.zh.soir;
      } else if (userLang.startsWith("ja")) {
        carteMidi = cartes.ja.midi;
        carteSoir = cartes.ja.soir;
      } else {
        // Par défaut, anglais
        carteMidi = cartes.en.midi;
        carteSoir = cartes.en.soir;
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
