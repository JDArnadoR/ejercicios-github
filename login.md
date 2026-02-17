# Esquema de Login

## 1. Descripción General

El sistema de login permite a los usuarios autenticarse mediante credenciales (usuario o email y contraseña) para acceder a la aplicación.

---

## 2. Campos del Formulario

### Email o Usuario

- Tipo: `text` / `email`
- Obligatorio: Sí
- Validación: Formato válido (si es email)

### Contraseña

- Tipo: `password`
- Obligatorio: Sí
- Validación: Mínimo 8 caracteres

### Recordarme

- Tipo: `checkbox`
- Obligatorio: No

### Botón Iniciar Sesión

- Tipo: `submit`

---

## 3. Flujo de Autenticación

1. El usuario ingresa sus credenciales.
2. El sistema valida los campos en el frontend.
3. Se envían los datos al servidor.
4. El servidor:
   - Verifica que el usuario exista.
   - Compara la contraseña utilizando hash seguro.
5. Resultado:
   - Acceso concedido si las credenciales son correctas.
   - Mensaje de error si son incorrectas.

---

## 4. Validaciones

### Frontend

- Campos obligatorios.
- Validación de formato de email.
- Longitud mínima de contraseña.

### Backend

- Verificación de existencia del usuario.
- Comparación segura de contraseña (hash + salt).
- Limitación de intentos de inicio de sesión.

---

## 5. Manejo de Errores

- Usuario no encontrado.
- Contraseña incorrecta.
- Cuenta bloqueada.
- Error interno del servidor.

---

## 6. Seguridad Recomendada

- Uso de HTTPS.
- Almacenamiento seguro de contraseñas (bcrypt, Argon2).
- Gestión de sesiones mediante JWT o sesiones tradicionales.
- Protección CSRF.
- Expiración automática de sesión por inactividad.
