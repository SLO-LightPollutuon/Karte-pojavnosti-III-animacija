<!DOCTYPE html>
<html lang="sl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animacija Svetlobnega Onesnaženja</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        img { animation: fadeIn 2s ease-in-out; width: 80%; max-width: 600px; }
    </style>
</head>
<body>
    
    <h2>Animacija svetlobnega onesnaženja v Sloveniji (2022)</h2>
    <p>Ta animacija prikazuje minimalne vrednosti radiance v Sloveniji in njeni okolici na podlagi podatkov NOAA VIIRS.</p>
    
    <input type="range" min="1" max="10" value="1" id="slider" oninput="updateImage()">
    <br>
    <img id="image" src="frame1.png" alt="Animacija svetlobnega onesnaženja">
    
    <script>
        function updateImage() {
            var frame = document.getElementById("slider").value;
            document.getElementById("image").src = "frame" + frame + ".png";
        }
    </script>
    
    <h2>Svetlobno onesnaženje po mestih</h2>
    <canvas id="radianceChart" width="400" height="200"></canvas>
    
    <script>
        var ctx = document.getElementById('radianceChart').getContext('2d');
        var myChart = new Chart(ctx, {
            type: 'bar',
            data: {
                labels: ['Ljubljana', 'Maribor', 'Koper', 'Celje', 'Novo Mesto'],
                datasets: [{
                    label: 'Radiance (mW/cm²/sr)',
                    data: [18, 15, 12, 10, 9],
                    backgroundColor: 'rgba(255, 99, 132, 0.5)',
                    borderColor: 'rgba(255, 99, 132, 1)',
                    borderWidth: 1
                }]
            },
            options: {
                scales: {
                    y: { beginAtZero: true }
                }
            }
        });
    </script>
    
    <h2>Interaktivni zemljevid</h2>
    <p>
        🌍 <a href="https://www.lightpollutionmap.info" target="_blank">Oglej si interaktivni zemljevid</a>
    </p>
    
</body>
</html>
