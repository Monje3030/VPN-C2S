# Laboratorio: VPN Client-to-Site con FortiGate 🛡️

## 📌 1. Topología del Proyecto
Se implementó una arquitectura de red segmentada utilizando GNS3, conectando dos redes locales a través de un Firewall FortiGate que actúa como terminador de VPN SSL.

<img width="922" height="710" alt="image" src="https://github.com/user-attachments/assets/ed0fc2c5-dd83-4ad0-91e6-51b9ad808866" />

## ⚙️ 2. Configuración Técnica

### A. SSL-VPN Settings & Pool
Se configuró un pool de direcciones dinámicas y un portal de acceso total (Full Access) sin Split-Tunneling para asegurar la inspección de todo el tráfico remoto.

<img width="843" height="220" alt="image" src="https://github.com/user-attachments/assets/b5ecae8b-5855-4a53-9eaf-0445ecc3027b" />

### B. Políticas de Firewall (Inter-LAN)
Para permitir que la LAN 1 hable con la LAN 2 "mediante el enlace VPN", se crearon políticas que vinculan la interfaz virtual `ssl.root` con los puertos físicos.

<img width="898" height="749" alt="image" src="https://github.com/user-attachments/assets/a75661c5-d6dc-45db-b125-2523c9e44146" />

## 🧪 3. Pruebas de Conectividad (Evidencias)

### Verificación de Tráfico (Sniffer)
Utilizamos el sniffer de paquetes para demostrar que el tráfico ICMP cruza el firewall correctamente entre el Port 2 y el Port 3.

<img width="921" height="672" alt="image" src="https://github.com/user-attachments/assets/cee42206-0f2d-4a26-9acc-2311d819c240" />

### Prueba de Enrutamiento (Trace-route)
El comando `trace` confirma que el primer salto es el gateway seguro del FortiGate, llegando exitosamente al destino final.

<img width="1076" height="300" alt="image" src="https://github.com/user-attachments/assets/7e27ae7c-9cbd-4f45-97a5-5e368c9b963f" />

## Video demostrativo

https://youtu.be/uyd1xR3IB3Y
