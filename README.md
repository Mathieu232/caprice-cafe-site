<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="refresh" content="0">
  <title>Carte du Caprice Café</title>
  <script>
    window.onload = function () {
      const now = new Date();
      const hour = now.getHours();
      const minutes = now.getMinutes();
      const totalMinutes = hour * 60 + minutes;

      // Créneaux horaires modifiés
      const midiStart = 8 * 60;       // Début du midi à 8h00
      const midiEnd = 17 * 60;        // Fin du midi à 17h00
      const soirStart = 17 * 60;      // Début du soir à 17h00
      const soirEnd = 23 * 60;        // Fin du soir à 23h00

      // Liens des cartes (en français)
      const carteMidiFr = "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link";
      const carteSoirFr = "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link";

      let carteMidi, carteSoir;

      // Redirection en fonction des horaires
      if (totalMinutes >= midiStart && totalMinutes < soirStart) {
        carteMidi = carteMidiFr;
        carteSoir = carteSoirFr;
        window.location.href = carteMidi; // Redirige vers la carte du midi
      } else if (totalMinutes >= soirStart && totalMinutes <= soirEnd) {
        carteMidi = carteMidiFr;
        carteSoir = carteSoirFr;
        window.location.href = carteSoir; // Redirige vers la carte du soir
      } else {
        document.getElementById("message").style.display = "block"; // Affiche un message si en dehors des horaires
      }
    };
  </script>
</head>
<body>
  <div id="message" style="display:none; text-align:center; margin-top: 50px;">
    <h2>Le Caprice Café vous accueille prochainement !</h2>
    <p>Les cartes sont disponibles de 8h00 à 17h00 (midi) et de 17h00 à 23h00 (soir).</p>
    <p><a href="https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link">Voir la carte du midi (PDF)</a></p>
    <p><a href="https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link">Voir la carte du soir (PDF)</a></p>
  </div>
</body>
</html>
