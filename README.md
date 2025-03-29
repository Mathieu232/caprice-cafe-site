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

      // Créneaux d'affichage : midi (11h30–17h), soir (17h–22h30)
      const midiStart = 11 * 60 + 30;
      const midiEnd = 17 * 60;
      const soirStart = 17 * 60;
      const soirEnd = 22 * 60 + 30;

      // Conditions selon l'heure
      if (totalMinutes >= midiStart && totalMinutes < soirStart) {
        window.location.href = "https://drive.google.com/file/d/1otbXLyysaZFH9PSm3orAujO7NF6AEBNj/view?usp=drive_link";
      } else if (totalMinutes >= soirStart && totalMinutes <= soirEnd) {
        window.location.href = "https://drive.google.com/file/d/1XDUFJ8YC9kNunZbjnbg2LgZkg7bi5SQV/view?usp=drive_link";
      } else {
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
