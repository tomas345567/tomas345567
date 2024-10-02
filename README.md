<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Configuración de Usuario</title>
    <link rel="stylesheet" href="./css/ajustes.css">
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }

        .container {
            max-width: 600px;
            margin: 20px auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 5px;
            background-color: #f9f9f9;
        }

        h2 {
            color: #333;
        }

        label {
            display: block;
            margin-bottom: 10px;
        }
    </style>
</head>

<body>
    <header class="header">
        <div class="logo"><img src="./img/Inicio-Photoroom.png-Photoroom.png" width="200px"></div>
        <input type="checkbox" id="toggle">
        <label for="toggle"><img class="menu" src="./img/Inicio.png" alt="menu"></label>
        <nav class="navigation">
            <ul>
                <li><a href="#">Inicio</a></li>
                <li><a href="#">Consejos</a></li>
                <li><a href="#">Marketing</a>
                    <ul>
                        <li><a href="#">13</a></li>
                        <li><a href="#">12</a></li>
                        <li><a href="#">11</a></li>
                        <li><a href="#">10</a>
                            <ul>
                                <li><a href="#">9</a></li>
                                <li><a href="#">8</a></li>
                                <li><a href="#">7</a></li>
                                <li><a href="#">6</a></li>
                            </ul>
                        </li>
                    </ul>
                </li>
                <li><a href="#">Proveedores</a>
                    <ul>
                        <li><a href="./index.html">que es provedores</a></li>
                        <li><a href="./funcion.html">como funcionan</a></li>
                        <li><a href="./operan.html">como operan </a></li>

                    </ul>
                </li>
                <li><a href="#">Finanzas</a></li>
                <li><a href="./ajustes.html"><img src="./img/configuraciones.png" alt="Configuración" class="config-icon"
                        width="30px"></a></li>
            </ul>
        </nav>
        <a href=""></a>
    </header>
    <div class="hero"></div>

    <div class="settings-container">
        <h1>configuracion</h1>
        <div class="settings-section">
            <h2>Cambiar Contraseña</h2>
            <form action="#" method="post">
                <label for="current-password">Contraseña Actual:</label>
                <input type="password" id="current-password" name="current-password" required>

                <label for="new-password">Nueva Contraseña:</label>
                <input type="password" id="new-password" name="new-password" required>

                <label for="confirm-password">Confirmar Contraseña:</label>
                <input type="password" id="confirm-password" name="confirm-password" required>

                <button type="submit">Cambiar Contraseña</button>
            </form>
        </div>

        <div class="settings-section">
            <h2>Configuración de Notificaciones</h2>
            <form id="notificationForm">
                <label for="email-notifications">Notificaciones por Correo Electrónico:</label>
                <input type="checkbox" id="email-notifications" name="email-notifications" checked>

                <label for="sms-notifications">Notificaciones por SMS:</label>
                <input type="checkbox" id="sms-notifications" name="sms-notifications">

                <button type="submit">Guardar Cambios</button>
            </form>
        </div>

        <div class="settings-section">
            <h2>Configuración de Idiomas</h2>
            <form action="#" method="post">
                <label for="language">Idioma Preferido:</label>
                <select id="language" name="language">
                    <option value="es" selected>Español</option>
                    <option value="en">Inglés</option>
                    <option value="fr">Francés</option>
                    <option value="de">Alemán</option>
                    <option value="it">Italiano</option>
                    <option value="pt">Portugués</option>
                </select>
                <button type="submit">Guardar Cambios</button>
            </form>
        </div>
    </div>
    <div class="settings-container">
        <h2>configuracion de privacidad</h2>
        <form id="privacySettingsForm">
            <label>
                <input type="checkbox" id="emailNotificationsCheckbox" checked> Recibir notificaciones por correo electrónico
            </label>
            <label>
                <input type="checkbox" id="popupNotificationsCheckbox"> Mostrar notificaciones emergentes en el sitio
            </label>
            <button type="button" id="savePrivacySettingsButton">Guardar cambios</button>
        </form>
    </div>
    <h3>Foto de Perfil</h3>
    <div class="profile-picture">
        <img id="profile-image" src="default-profile.jpg" alt="Foto de perfil">
        <input type="file" id="profile-image-input" accept="image/*">
        <label for="profile-image-input">selecciona una imagen</label>
    </div>

    <div class="settings-container">
        <h2>Eliminar Cuenta</h2>
        <form action="#" method="post" id="deleteAccountForm">
            <div class="settings-section">
                <h3>Confirmación de Seguridad</h3>
                <label for="password">Contraseña:</label>
                <input type="password" id="password" name="password" required>
            </div>
            <div class="settings-section">
                <h3>Advertencia</h3>
                <p>Al eliminar tu cuenta, perderás todos tus datos y configuraciones asociadas. Esta acción no se puede deshacer. Por favor, asegúrate de querer eliminar tu cuenta antes de continuar.</p>
            </div>
            <button type="submit">Eliminar Cuenta</button>
        </form>
    </div>
    <div class="settings-section">
        <h2>Preferencias de Privacidad de Datos</h2>
        <label for="profile-visibility">Visibilidad del Perfil:</label>
        <select id="profile-visibility" name="profile-visibility">
            <option value="public">Público</option>
            <option value="private">Privado</option>
        </select>
        <label for="data-sharing">Compartir Datos con Terceros:</label>
        <input type="checkbox" id="data-sharing" name="data-sharing" checked>
        <button type="submit">Guardar Cambios</button>
    </div>
</body>

<script>
    document.getElementById('notificationForm').addEventListener('submit', function(event) {
        event.preventDefault();
        
        const formData = new FormData(event.target);
        const notificationSettings = {};
        
        for (var pair of formData.entries()) {
            notificationSettings[pair[0]] = pair[1] === 'on';
        }
        
        
        console.log(notificationSettings);
    });

    document.getElementById('savePrivacySettingsButton').addEventListener('click', function() {
        const emailNotifications = document.getElementById('emailNotificationsCheckbox').checked;
        const popupNotifications = document.getElementById('popupNotificationsCheckbox').checked;
        
        
        console.log("Email Notifications:", emailNotifications);
        console.log("Popup Notifications:", popupNotifications);
    });
</script>

</html>
