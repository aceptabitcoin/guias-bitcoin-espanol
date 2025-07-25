# 🔐 Conectar GitHub con SSH desde la terminal (macOS / Linux)

> Guía profesional y paso a paso para configurar una clave SSH, agregarla a GitHub y trabajar desde la terminal con autenticación segura.
>
> Checa este link version en ingles y abajo te doy el paso paso 
> https://docs.github.com/en/authentication/connecting-to-github-with-ssh

---

## ✅ ¿Qué vas a lograr con esta guía?

- Generar una clave SSH segura
- Asociarla a tu cuenta de GitHub
- Clonar y subir contenido a repositorios de GitHub sin usar usuario y contraseña

---

## 🛠 Requisitos

- Git instalado
- Cuenta de GitHub activa
- Acceso a una terminal (macOS o Linux)

---

## 1️⃣ Instalar Git (si no lo tienes)

Abre terminal desde tu dispositivo MAC WINDOWS LINUX 

Verifica si ya lo tienes:

```bash
git --version
```

Si el comando no existe, en macOS puedes instalar Git ejecutando:

```bash
xcode-select --install
```

En distribuciones de Linux (Debian/Ubuntu):

```bash
sudo apt update && sudo apt install git
```

---

## 2️⃣ Generar una clave SSH

En tu terminal, ejecuta:

```bash
ssh-keygen -t ed25519 -C "tu-correo@example.com"
```

Cuando aparezca:

```
Enter file in which to save the key (/home/usuario/.ssh/id_ed25519):
```

✅ Pulsa `Enter` para aceptar la ubicación por defecto.

Luego:

```
Enter passphrase (empty for no passphrase):
```

✅ Puedes dejarlo vacío o ingresar una frase segura (recomendado).

---

## 3️⃣ Agregar la clave SSH al agente de autenticación

Primero activa el agente:

```bash
eval "$(ssh-agent -s)"
```

Agrega tu clave privada:

```bash
ssh-add ~/.ssh/id_ed25519
```

---

## 4️⃣ Copiar tu clave pública

Para copiar al portapapeles:

- En macOS:

```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

- En Linux (requiere `xclip`):

```bash
xclip -sel clip < ~/.ssh/id_ed25519.pub
```

O bien puedes ver la clave y copiarla manualmente:

```bash
cat ~/.ssh/id_ed25519.pub
```

---

## 5️⃣ Agregar tu clave pública en GitHub

1. Inicia sesión en [https://github.com](https://github.com)
2. Ve a: `Settings` → `SSH and GPG keys`
3. Haz clic en **"New SSH Key"**
4. Título: escribe un nombre descriptivo (ej. “Mi Laptop”)
5. Pega la clave pública
6. Clic en **"Add SSH Key"**

---

## 6️⃣ Verificar conexión con GitHub

En tu terminal:

```bash
ssh -T git@github.com
```

Si es la primera vez, aparecerá algo como:

```
The authenticity of host 'github.com' can't be established...
Are you sure you want to continue connecting (yes/no)?
```

✅ Escribe:

```bash
yes
```

🟢 Si todo está bien, verás:

```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

---

## 7️⃣ Clonar un repositorio usando SSH

1. Ve a tu repositorio en GitHub
2. Clic en el botón `Code` → selecciona `SSH`
3. Copia la URL (ejemplo):

```
git@github.com:usuario/repositorio.git
```

4. En la terminal:

```bash
git clone git@github.com:usuario/repositorio.git
```

---

## 8️⃣ Subir archivos desde la terminal (pasos estándar)

1. Agrega tu archivo o carpeta:

```bash
git add nombre-del-archivo.md
```

2. Haz un commit con un mensaje:

```bash
git commit -m "Agregar guía SSH"
```

3. Sube los cambios a GitHub:

```bash
git push origin main
```

---

## 🧠 Comando útil para verificar si estás usando SSH

```bash
git remote -v
```

🟢 Salida esperada:

```
origin  git@github.com:usuario/repositorio.git (fetch)
origin  git@github.com:usuario/repositorio.git (push)
```

---

## 📌 Referencias

- [Guía oficial de GitHub - SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

---

## ✍️ Créditos

Esta guía forma parte del repositorio de educación en español sobre Bitcoin:  
[https://github.com/aceptabitcoin/guias-bitcoin-espanol](https://github.com/aceptabitcoin/guias-bitcoin-espanol)
