<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="refresh" content="0">
  <title>Carte du Caprice Café</title>
  <script>
    window.onload = function () {
      const userLang = navigator.language || navigator.userLanguage; // Détection de la langue du navigateur
      document.getElementById("langueDetectee").innerHTML = "Langue détectée : " + userLang; // Affichage de la langue détectée
      
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

      let carteMidi, carteSoir;

      // Vérifier la langue de l'utilisateur et rediriger en fonction
      if (userLang.startsWith("fr")) {
        carteMidi = carteMidiFr;
        carteSoir = carteSoirFr;
      } else if (userLang.startsWith("en")) {
        carteMidi = carteMidiEn;
        carteSoir = carteSoirEn;
      } else {
        // Par défaut, anglais
        carteMidi = carteMidiEn;
        carteSo
