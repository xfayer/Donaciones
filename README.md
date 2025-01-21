<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Donaciones para Siria</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
        }
        header {
            background: #d9534f;
            color: #fff;
            padding: 10px 20px;
            text-align: center;
        }
        .container {
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background: #fff;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        h1, h2 {
            color: #d9534f;
        }
        .btn {
            display: inline-block;
            background: #d9534f;
            color: #fff;
            padding: 10px 15px;
            text-decoration: none;
            border-radius: 5px;
            margin-top: 10px;
        }
        .btn:hover {
            background: #c9302c;
        }
        #paypal-button-container {
            margin-top: 20px;
        }
        footer {
            text-align: center;
            padding: 10px 20px;
            background: #222;
            color: #fff;
            margin-top: 20px;
        }
    </style>
    <script src="https://www.paypal.com/sdk/js?client-id=AWbQbAq1g4E_dSJ0_HLCOJYbryXGKFMnGYEjoJeXJjD60JFcoTZ_U_QACHZME-NC1Tzoc8KzoTKH3__6&currency=USD"></script>
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            paypal.Buttons({
                createOrder: function(data, actions) {
                    return actions.order.create({
                        purchase_units: [{
                            amount: {
                                value: '10.00' // Monto fijo de donación, puedes hacerlo dinámico
                            }
                        }]
                    });
                },
                onApprove: function(data, actions) {
                    return actions.order.capture().then(function(details) {
                        alert('Gracias, ' + details.payer.name.given_name + ', tu donación ha sido procesada con éxito.');
                    });
                }
            }).render('#paypal-button-container');
        });
    </script>
</head>
<body>
    <header>
        <h1>Ayuda a Siria</h1>
        <p>Juntos podemos marcar la diferencia</p>
    </header>

    <div class="container">
        <h2>¿Por qué donar?</h2>
        <p>
            Siria enfrenta una crisis humanitaria devastadora debido al conflicto que ha afectado al país durante años. Millones de familias han perdido sus hogares, carecen de alimentos, agua potable y acceso a atención médica básica. 
        </p>
        <p>
            Tu donación puede proporcionar ayuda vital como alimentos, ropa, refugio y apoyo médico a quienes más lo necesitan.
        </p>

        <h2>¿Cómo se usarán tus donaciones?</h2>
        <ul>
            <li>Distribución de alimentos y agua potable</li>
            <li>Provisión de refugios temporales</li>
            <li>Acceso a atención médica y medicamentos</li>
            <li>Apoyo psicológico para niños y familias</li>
        </ul>

        <h2>Haz tu donación</h2>
        <p>
            Cada contribución, grande o pequeña, marca la diferencia. Por favor, considera realizar una donación hoy.
        </p>

        <div id="paypal-button-container"></div>

        <p>Si tienes alguna pregunta, por favor contáctanos a <a href="mailto:ayuda@siria.org">ayuda@siria.org</a>.</p>
    </div>

    <footer>
        <p>&copy; 2025 Ayuda a Siria. Todos los derechos reservados.</p>
    </footer>
</body>
</html>
