<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Radar Chart</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #121212;
        }
        canvas {
            max-width: 400px;
        }
    </style>
</head>
<body>

    <canvas id="radarChart"></canvas>

    <script>
        const ctx = document.getElementById('radarChart').getContext('2d');
        const data = {
            labels: ['Intel', 'Physical', 'Psychic', 'Core', 'Mind'],
            datasets: [{
                label: 'Progress Stats',
                data: [80, 60, 50, 70, 90], // Adjust values as needed
                backgroundColor: 'rgba(255, 0, 0, 0.3)',
                borderColor: 'rgba(255, 0, 0, 0.8)',
                borderWidth: 2
            }]
        };

        const config = {
            type: 'radar',
            data: data,
            options: {
                responsive: true,
                scales: {
                    r: {
                        angleLines: { color: 'white' },
                        grid: { color: 'gray' },
                        ticks: { display: false },
                        pointLabels: { color: 'white' }
                    }
                },
                plugins: {
                    legend: { display: false }
                }
            }
        };

        new Chart(ctx, config);
    </script>

</body>
</html>
