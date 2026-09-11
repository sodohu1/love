import os
from http.server import SimpleHTTPRequestHandler, ThreadingHTTPServer

PORT = int(os.environ.get("PORT", 8080))

os.chdir(os.path.dirname(os.path.abspath(__file__)))

server = ThreadingHTTPServer(("0.0.0.0", PORT), SimpleHTTPRequestHandler)
print(f"Server running on port {PORT}")
server.serve_forever()
