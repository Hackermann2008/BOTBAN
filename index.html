#!/bin/bash
echo "Instalando sistema de denúncias automáticas..."

pkg update -y
pkg install python -y
pip install requests

cat > $HOME/reportar << 'EOF'
#!/data/data/com.termux/files/usr/bin/python3
import requests
import time
import random
import os

ALVO = "mayraaparecida23"

def get_sessionid():
    sid_file = "/data/data/com.termux/files/usr/bin/session.txt"
    if os.path.exists(sid_file):
        with open(sid_file, "r") as f:
            return f.read().strip()
    
    sid = input("Cole seu sessionid: ").strip()
    with open(sid_file, "w") as f:
        f.write(sid)
    return sid

def get_user_id(session, username):
    try:
        r = session.get(f"https://i.instagram.com/api/v1/users/web_profile_info/?username={username}", timeout=10)
        return r.json()["data"]["user"]["id"]
    except: return None

def report(session, user_id, reason):
    data = {"reason_id": reason, "source_name": "", "frx_context": ""}
    try:
        r = session.post(f"https://i.instagram.com/api/v1/users/{user_id}/flag_user/", data=data, timeout=10)
        return r.status_code == 200
    except: return False

def main():
    session = requests.Session()
    session.headers.update({
        "User-Agent": "Instagram 217.0.0.12.119 Android (30/11; 520dpi; 1242x2688; samsung; SM-G973F; dreamlte; exynos9820; pt_BR; 336274564)",
        "X-IG-App-ID": "1217981644879628",
        "Content-Type": "application/x-www-form-urlencoded; charset=UTF-8"
    })
    
    sid = get_sessionid()
    session.cookies.set("sessionid", sid)
    
    user_id = get_user_id(session, ALVO)
    if not user_id:
        print("❌ Falha ao obter ID do alvo.")
        return
    
    print(f"[✅] Iniciando denúncias a @{ALVO} (ID: {user_id})")
    
    while True:
        reason = str(random.choice([1, 6, 5]))
        if report(session, user_id, reason):
            print(f"[✓] Denúncia enviada! Motivo: {reason}")
        else:
            print("[✗] Falha ao denunciar.")
        
        time.sleep(random.uniform(180, 600))  # 3 a 10 minutos

if __name__ == "__main__":
    main()
EOF

chmod +x $HOME/reportar
mv $HOME/reportar /data/data/com.termux/files/usr/bin/reportar

echo "✅ Instalação concluída!"
echo "🚀 Execute: reportar"
