# Library App

App móvil de biblioteca hecha con [Expo](https://expo.dev) y Expo Router. Permite registrarse, iniciar sesión, explorar libros y gestionar préstamos, con almacenamiento local en SQLite y sincronización con un servidor.

## Características

- Registro e inicio de sesión
- Catálogo de libros y detalle de cada libro
- Gestión de préstamos
- Perfil de usuario
- Funcionamiento offline con base de datos local (SQLite) y sincronización
- Aviso de estado de conexión

## Tecnologías

- Expo + Expo Router (navegación basada en archivos)
- React Native y TypeScript
- expo-sqlite
- Jest para pruebas

## Requisitos

- Node.js 20 o superior
- [Expo Go](https://expo.dev/go) en tu celular, o un emulador Android/iOS
- Un backend en ejecución (la URL se configura abajo)

## Configuración

1. Instala las dependencias:

   ```bash
   npm install
   ```

2. Crea tu archivo de entorno a partir del ejemplo:

   ```bash
   cp .env.example .env
   ```

3. Edita `.env` y completa la URL de tu API:

   ```
   EXPO_PUBLIC_API_URL=http://192.168.x.x:3000
   ```

   > Si pruebas en un celular físico, usa la IP de tu PC en la red local, no `localhost`.
   > Las variables con prefijo `EXPO_PUBLIC_` quedan visibles dentro de la app: nunca pongas claves secretas ahí.

4. Inicia la app:

   ```bash
   npx expo start -c
   ```

   Escanea el QR con Expo Go (el celular y la PC deben estar en la misma red Wi-Fi).

## Pruebas

```bash
npm test
```

## Estructura del proyecto

```
src/
├── app/          # Pantallas y rutas (Expo Router)
├── components/   # Componentes reutilizables
├── config/       # Lectura de variables de entorno
├── db/           # Migraciones y repositorios SQLite
├── hooks/        # Hooks personalizados
├── lib/          # Utilidades
├── providers/    # Contextos de autenticación y datos
├── services/     # API, autenticación, préstamos y sincronización
└── types/        # Tipos de TypeScript
__tests__/        # Pruebas unitarias e integración
test-utils/       # Utilidades para pruebas
```

## Licencia

MIT
