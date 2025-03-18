# 🌍 Statistične vrednosti radianc v Sloveniji in okolici (2022)

Ta repozitorij vsebuje vizualizacijo **minimalnih, povrepnih in maksimalnih vrednosti radiance** v Sloveniji in okolici za leto **2022**. 

## 📌 Animacija svetlobne onesnaženosti

---

### <h2 align="center"><b>Slovenija in okolica 2022</b></h2>

<div style="border: 3px solid black; padding: 10px; display: inline-block;">
    <img src="KDE.gif" width="100%">
</div>

---

## 📊 Svetlobno onesnaženje po mestih

<canvas id="radianceChart" width="400" height="200"></canvas>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script>
    var ctx = document.getElementById('radianceChart').getContext('2d');
    var myChart = new Chart(ctx, {
        type: 'bar',
        data: {
            labels: ['Ljubljana', 'Maribor', 'Koper', 'Celje', 'Novo Mesto'],
            datasets: [{
                label: 'Radiance (mW/cm²/sr)',
                data: [18, 15, 12, 10, 9], // Prilagodi s pravimi podatki
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

## 🔗 Povezave
🌍 [NASA Earthdata - Nighttime Lights](https://www.earthdata.nasa.gov/topics/human-dimensions/nighttime-lights)  
🌍 [NASA Worldview](https://worldview.earthdata.nasa.gov/?)
🌍 [Temno Nebo Slovenija](http://www.temnonebo.si/)
