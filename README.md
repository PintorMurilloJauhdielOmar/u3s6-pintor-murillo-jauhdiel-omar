# Proyecto Django — Pintor Murillo Jauhdiel

## Demo en vivo (producción)

https://u3s6-pintor-murillo-jauhdiel-omar.onrender.com/login/?next=/servicios/

## Semana 6 — Autenticación, sesiones y protección de vistas

### De qué trató la práctica

Se agregó un sistema de autenticación al proyecto Django. El módulo de **servicios** (el CRUD de la semana 5) quedó protegido: solo se puede entrar con una sesión iniciada.

- **Inicio de sesión (login):** el usuario se autentica con sus credenciales y Django crea la sesión.
- **Vistas protegidas:** al entrar a `/servicios/` sin sesión, Django redirige a `/login/?next=/servicios/`. Después de iniciar sesión, regresa a la página que se pidió. Ese es el parámetro `next`.
- **Cierre de sesión (logout):** termina la sesión del usuario.
- **CRUD de servicios:** crear, listar, editar y eliminar registros, ahora solo para usuarios autenticados, sobre la base de datos MySQL en la nube.
- **Despliegue en Render:** la app corre en producción con variables de entorno (`.env.example` como plantilla) y archivos estáticos en `staticfiles`.

### Estructura del proyecto

```
core/                     # App principal (modelos, vistas, templates)
miproyecto_djangopmjo/    # Configuración del proyecto (settings, urls)
staticfiles/              # Archivos estáticos para producción
.env.example              # Plantilla de variables de entorno
manage.py
requirements.txt
```

### Cómo correrlo en local

```bash
pip install -r requirements.txt
cp .env.example .env      # y llenar los datos de la base de datos
python manage.py migrate
python manage.py runserver
```

## Recordatorio para la próxima práctica

- [ ] Poner la captura de **Not Found** (ruta que no existe).
- [ ] Poner la captura de **Iniciar sesión** (el login al que redirige `?next=/servicios/`).
- [ ] Revisar que el link de Render abra directo en el login.
- [ ] Antes de entregar: `git push` y confirmar que Render terminó el redeploy.
