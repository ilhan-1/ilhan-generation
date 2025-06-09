from flask import Flask, render_template_string, Response

app = Flask(__name__)

HTML = '''
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>ilhaangeneration.com</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <style>
        body {
            margin: 0;
            background: #000;
            color: gold;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            text-align: center;
            padding: 40px;
        }
        .logo {
            width: 240px;
            height: auto;
            margin-bottom: 30px;
            filter: drop-shadow(0 0 15px gold);
        }
        h1 {
            font-size: 3em;
            margin: 0.3em 0;
        }
        p {
            font-size: 1.2em;
            color: #ccc;
        }
        footer {
            position: fixed;
            bottom: 10px;
            width: 100%;
            font-size: 0.9em;
            color: #555;
        }
        @media(max-width: 600px) {
            h1 { font-size: 2em; }
            .logo { width: 160px; }
        }
    </style>
</head>
<body>
    <img src="/logo.svg" alt="Lion Logo" class="logo">
    <h1>ilhaangeneration.com</h1>
    <p>The future of AI-generated videos and photos</p>
    <footer>&copy; 2025 ilhaan generation. All rights reserved.</footer>
</body>
</html>
'''

# SVG Lion Logo — clean, gold-on-black stylized lion head
SVG_LOGO = '''
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" width="240" height="240">
  <circle cx="256" cy="256" r="250" fill="black" stroke="gold" stroke-width="10"/>
  <circle cx="190" cy="190" r="30" fill="gold"/>
  <circle cx="320" cy="190" r="30" fill="gold"/>
  <path d="M190 320 Q256 380 320 320" stroke="gold" stroke-width="10" fill="none" />
  <path d="M100 100 Q256 0 412 100 Q512 256 412 412 Q256 512 100 412 Q0 256 100 100 Z" 
        stroke="gold" stroke-width="8" fill="none"/>
</svg>
'''

@app.route('/')
def home():
    return render_template_string(HTML)

@app.route('/logo.svg')
def logo_svg():
    return Response(SVG_LOGO, mimetype='image/svg+xml')

if __name__ == '__main__':
    print("🚀 Launching: http://127.0.0.1:5000")
    app.run(debug=True)
