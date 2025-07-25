git add conectar_github_con_ssh.md
git commit -m "Actualización: guía profesional para conectar GitHub con SSH"
git push origin main
# 🔐 Conectar GitHub con SSH en macOS

> Guía práctica para mejorar la seguridad al autenticarte con GitHub usando claves SSH.  
> Basado en: [GitHub Docs - Connecting to GitHub with SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

---

## ✅ ¿Por qué usar SSH con GitHub?

El uso de claves SSH permite una conexión segura entre tu máquina local y GitHub, eliminando la necesidad de ingresar usuario y contraseña o tokens cada vez que haces `push` o `pull`. Es altamente recomendado para desarrolladores y contribuyentes activos en proyectos de código abierto.

---

## 🛠 Requisitos previos

- Tener Git instalado:
  
  ```bash
  git --version

