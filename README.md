<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Weapon Detection System</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
            color: #333;
        }
        .container {
            width: 90%;
            margin: auto;
            overflow: hidden;
            padding: 20px;
            background: #fff;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
        h1, h2, h3 {
            color: #444;
        }
        code {
            background: #eee;
            padding: 2px 4px;
            border-radius: 4px;
        }
        pre {
            background: #f8f8f8;
            padding: 10px;
            border-left: 3px solid #ccc;
            overflow-x: auto;
        }
        ul {
            padding-left: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Weapon Detection System</h1>

        <h2>Overview</h2>
        <p>This project implements a weapon detection system using the YOLOv8 framework. The system is capable of identifying and localizing weapons in images or videos, making it ideal for security and surveillance applications.</p>

        <h2>Features</h2>
        <ul>
            <li><strong>Real-Time Detection:</strong> Accurately detects and annotates weapons with bounding boxes.</li>
            <li><strong>Custom Dataset:</strong> Trained on a dataset containing nine classes of weapons.</li>
            <li><strong>User-Friendly Interface:</strong> Integrated with Gradio for seamless interaction and testing.</li>
        </ul>

        <h2>Dataset</h2>
        <p>The model is trained on a custom dataset comprising images of nine weapon classes. The dataset ensures balanced representation across all classes for accurate predictions.</p>

        <h2>Technologies Used</h2>
        <ul>
            <li><strong>YOLOv8 Framework:</strong> For training and deploying the object detection model.</li>
            <li><strong>Gradio:</strong> To create a web-based interface for testing the model.</li>
            <li><strong>Python:</strong> Primary programming language for model development.</li>
            <li><strong>Google Colab:</strong> For training and testing the model in a cloud environment.</li>
        </ul>

        <h2>Setup and Usage</h2>
        <ol>
            <li>Clone the repository:
                <pre><code>git clone https://github.com/your-username/Weapon-Detection.git</code></pre>
            </li>
            <li>Install the required dependencies:
                <pre><code>pip install -r requirements.txt</code></pre>
            </li>
            <li>Train the model:
                <pre><code>
from ultralytics import YOLO
model = YOLO('yolov8s.pt')
model.train(data='data.yaml', epochs=20, imgsz=640, device=0)
                </code></pre>
            </li>
            <li>Test the model:
                <pre><code>
results = model.predict(source='path_to_test_images_or_videos')
                </code></pre>
            </li>
            <li>Launch the Gradio interface:
                <pre><code>
import gradio as gr

def detect_objects(image):
    results = model.predict(source=image)
    return results[0].plot()

interface = gr.Interface(fn=detect_objects, inputs=gr.Image(type="pil"), outputs=gr.Image(type="pil"), title="Weapon Detection")
interface.launch()
                </code></pre>
            </li>
        </ol>

        <h2>Results</h2>
        <p>The model demonstrates high accuracy in detecting weapons across all classes. It provides real-time performance suitable for deployment in security applications.</p>

        <h2>Applications</h2>
        <ul>
            <li>Security and Surveillance</li>
            <li>Public Safety Monitoring</li>
            <li>Risk Assessment in Sensitive Areas</li>
        </ul>

        <h2>Contributing</h2>
        <p>Contributions are welcome! Feel free to open issues or submit pull requests for improvements or bug fixes.</p>

        
    </div>
</body>
</html>
