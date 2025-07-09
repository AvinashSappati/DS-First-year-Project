<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Asteroid Hazard Prediction with Machine Learning</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <style>
        body {
            background: #181c20;
            color: #f2f2f2;
            font-family: 'Segoe UI', 'Roboto', Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 900px;
            margin: 40px auto;
            background: #23272b;
            border-radius: 14px;
            box-shadow: 0 6px 24px rgba(0,0,0,0.45);
            padding: 40px 32px 32px 32px;
        }
        h1, h2, h3 {
            color: #ffd166;
            margin-top: 0;
        }
        h1 {
            font-size: 2.8em;
            text-align: center;
            margin-bottom: 0.2em;
        }
        h2 {
            border-bottom: 2px solid #ffd166;
            padding-bottom: 4px;
            margin-top: 2em;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 18px 0;
        }
        th, td {
            padding: 8px 12px;
            border: 1px solid #444;
            text-align: left;
        }
        th {
            background: #ffd166;
            color: #23272b;
        }
        tr:nth-child(even) {
            background: #22272b;
        }
        tr:nth-child(odd) {
            background: #1a1e22;
        }
        code, pre {
            background: #22272b;
            color: #ffd166;
            padding: 2px 6px;
            border-radius: 4px;
            font-size: 1.05em;
        }
        .quote {
            font-style: italic;
            color: #a0c4ff;
            border-left: 4px solid #ffd166;
            padding-left: 16px;
            margin: 24px 0;
        }
        .project-structure {
            background: #1a1e22;
            padding: 16px;
            border-radius: 8px;
            font-family: 'Fira Mono', 'Consolas', monospace;
            color: #ffd166;
        }
        .contributors {
            display: flex;
            gap: 24px;
            flex-wrap: wrap;
        }
        .contributors span {
            background: #ffd166;
            color: #23272b;
            padding: 6px 14px;
            border-radius: 6px;
            font-weight: bold;
        }
        a {
            color: #06d6a0;
            text-decoration: none;
        }
        a:hover {
            text-decoration: underline;
        }
        .badge {
            display: inline-block;
            background: #06d6a0;
            color: #23272b;
            border-radius: 6px;
            padding: 3px 10px;
            font-size: 0.95em;
            margin-left: 10px;
        }
        @media (max-width: 600px) {
            .container { padding: 14px 2vw; }
            h1 { font-size: 2em; }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>🚀 Asteroid Hazard Prediction with Machine Learning</h1>
        <p style="text-align:center;">
            <span class="badge">NASA NEO Dataset</span>
            <span class="badge">Binary Classification</span>
            <span class="badge">Python</span>
        </p>

        <h2>📂 Overview</h2>
        <p>
            This project leverages NASA's Near-Earth Objects (NEO) dataset to build a <b>machine learning model</b> that predicts whether an asteroid is hazardous to Earth based on its physical and orbital characteristics.
        </p>
        <ul>
            <li><b>Dataset:</b> <a href="https://www.kaggle.com/datasets/sameepvani/nasa-nearest-earth-objects" target="_blank">Kaggle - NASA Nearest Earth Objects</a></li>
            <li><b>Goal:</b> Classify asteroids as <i>Hazardous</i> or <i>Non-Hazardous</i> using their parameters.</li>
        </ul>

        <h2>🗂️ Dataset Features</h2>
        <table>
            <tr><th>Feature</th><th>Description</th></tr>
            <tr><td>est_diameter_min</td><td>Estimated minimum diameter (km)</td></tr>
            <tr><td>est_diameter_max</td><td>Estimated maximum diameter (km)</td></tr>
            <tr><td>relative_velocity</td><td>Relative velocity (km/h)</td></tr>
            <tr><td>miss_distance</td><td>Closest approach distance to Earth (km)</td></tr>
            <tr><td>absolute_magnitude</td><td>Brightness of the asteroid</td></tr>
            <tr><td>orbiting_body</td><td>Orbiting celestial body (Earth for all rows)</td></tr>
            <tr><td>sentry_object</td><td>Sentry monitoring flag</td></tr>
            <tr><td>hazardous</td><td>Target: Is the asteroid hazardous? (True/False)</td></tr>
        </table>

        <h2>📊 Exploratory Data Analysis</h2>
        <ul>
            <li><b>Total records:</b> 90,836</li>
            <li><b>Key statistics:</b>
                <ul>
                    <li>Diameter ranges from <b>0.0006 km</b> to <b>37.89 km</b></li>
                    <li>Relative velocity up to <b>236,990 km/h</b></li>
                    <li>Miss distance as close as <b>6,746 km</b></li>
                </ul>
            </li>
        </ul>

        <h3>Outlier Detection</h3>
        <table>
            <tr><th>Feature</th><th>Outlier Count</th><th>Outlier %</th></tr>
            <tr><td>est_diameter_min</td><td>8,306</td><td>9.14%</td></tr>
            <tr><td>est_diameter_max</td><td>8,306</td><td>9.14%</td></tr>
            <tr><td>relative_velocity</td><td>1,574</td><td>1.73%</td></tr>
            <tr><td>miss_distance</td><td>0</td><td>0.00%</td></tr>
            <tr><td>absolute_magnitude</td><td>101</td><td>0.11%</td></tr>
        </table>

        <h2>🏆 Feature Importance</h2>
        <table>
            <tr><th>Feature</th><th>Importance</th></tr>
            <tr><td>est_diameter_max</td><td>0.9516</td></tr>
            <tr><td>miss_distance</td><td>0.0202</td></tr>
            <tr><td>relative_velocity</td><td>0.0182</td></tr>
            <tr><td>est_diameter_min</td><td>0.0070</td></tr>
            <tr><td>absolute_magnitude</td><td>0.0029</td></tr>
        </table>

        <h2>🤖 Models & Performance</h2>
        <table>
            <tr>
                <th>Model</th>
                <th>Recall</th>
                <th>Accuracy</th>
                <th>Precision</th>
            </tr>
            <tr>
                <td>Perceptron</td>
                <td>0.9572</td>
                <td>0.7769</td>
                <td>0.2938</td>
            </tr>
            <tr>
                <td>KNN (n=5)</td>
                <td>0.7582</td>
                <td>0.8411</td>
                <td>0.3469</td>
            </tr>
            <tr>
                <td>KNN (n=9)</td>
                <td>0.8265</td>
                <td>0.8254</td>
                <td>0.3322</td>
            </tr>
            <tr>
                <td>Decision Tree</td>
                <td>0.9832</td>
                <td>0.7839</td>
                <td>0.3037</td>
            </tr>
        </table>
        <ul>
            <li><b>Decision Tree</b> achieved the highest recall.</li>
            <li><b>KNN (n=5)</b> had the best accuracy.</li>
            <li><b>Precision</b> is generally low due to class imbalance.</li>
        </ul>

        <h2>🛠️ How to Run</h2>
        <ol>
            <li><b>Clone the repository:</b>
                <pre>git clone https://github.com/yourusername/asteroid-hazard-prediction.git
cd asteroid-hazard-prediction</pre>
            </li>
            <li><b>Install dependencies:</b>
                <pre>pip install -r requirements.txt</pre>
            </li>
            <li><b>Download the dataset:</b>
                <ul>
                    <li>Place <code>neo.csv</code> in the project directory.</li>
                </ul>
            </li>
            <li><b>Run the notebook:</b>
                <ul>
                    <li>Open <code>Mini_Project_Grp1.ipynb</code> in Jupyter Notebook or VS Code.</li>
                </ul>
            </li>
        </ol>

        <h2>📈 Results & Insights</h2>
        <ul>
            <li><b>Asteroid size</b> (<code>est_diameter_max</code>) is the most influential feature for hazard prediction.</li>
            <li><b>Recall</b> is prioritized to minimize missed hazardous asteroids.</li>
            <li><b>Class imbalance</b> affects precision; consider advanced techniques for improvement.</li>
        </ul>

        <h2>📝 Project Structure</h2>
        <div class="project-structure">
            ├── Mini_Project_Grp1.ipynb   # Main notebook<br>
            ├── neo.csv                   # Dataset (user provided)<br>
            ├── requirements.txt          # Python dependencies<br>
            └── README.md                 # Project documentation
        </div>

        <h2>🙌 Contributors</h2>
        <div class="contributors">
            <span>Your Name</span>
            <span>Collaborator 1</span>
            <span>Collaborator 2</span>
            <!-- Add more as needed -->
        </div>

        <h2>📜 License</h2>
        <p>
            This project is licensed under the MIT License.
        </p>

        <h2>⭐ Acknowledgments</h2>
        <ul>
            <li>NASA for the NEO dataset</li>
            <li>Kaggle for data hosting</li>
        </ul>

        <div class="quote">
            “Predicting asteroid hazards helps safeguard our planet—one model at a time.”
        </div>

        <p style="text-align:center; margin-top:32px;">
            <b>Feel free to fork, star, and contribute!</b>
        </p>
    </div>
</body>
</html>
