# Test

## Sección 1 - Conceptos teóricos de protractor

### Pregunta 1
¿Cuáles son las ventajas de automatizar pruebas?

1. Aumenta la capacidad de ejecución de pruebas.
2. Permite la integración continua.
3. Permite probar funcionalidades previas fácilmente.
4. Todas las anteriores.

> Respuesta [ 4 ]

###  Pregunta 2
¿Qué es Protractor?

1. Un framework de pruebas para aplicaciones web de cualquier tecnología.
2. Un framework de pruebas para aplicaciones web de Angular y AngularJS.
3. Una herramienta de testing para probar aplicaciones web.
4. Un módulo que permite implementar BDD.

> Respuesta [ 2 ]

### Pregunta 3
3. Los 3 grandes métodos de protractor para hacer las pruebas son: 

1. browser, click, element
2. isEnabled, sendKeys, expectedConditions
3. sendKeys, element, getCurrentUrl
4. browser, element, expectedConditions

> Respuesta [ 4 ]

### Pregunta 4
El método que me permite abrir una URL en el navegador es....

1. get()
2. openUrl()
3. getCurrentUrl()
4. browseUrl()

> Respuesta [1]

### Pregunta 5
El siguiente fragmento de código realiza lo siguiente:

   ```
    let nombre = element.(by.id(´campoNombre´))
    nombre.sendKeys("Alfredo")
```

1. Manda una clave aleatoria al campo cuyo identificador id es `campoNombre`
2. Escribe la cadena "Alfredo" en el elemento cuyo selector css es `campoNombre`
3. Hace click en el elemento campoNombre.
4. Escribe la cadena "Alfredo" en el campo cuyo identificador id es `campoNombre`

> Respuesta [4]

### Pregunta 6
Elija la afirmación correcta sobre los `expectedConditions`

1. No se puede combinar entre ellos.
2. Junto a browser.wait() nos permite realizar esperas automáticas
3. elementToBeClickable() no es un método de la clase.
4. No es una clase de protractor.

> Respuesta: [2]

### Pregunta 7

Elija la afirmación incorrecta del Page Object....

1. Evita código duplicado.
2. Mejora el mantenimiento de las pruebas.
3. Modela los elementos como objetos dentro del código de nuestros tests.
4. Su uso no es recomendable.

> Respuesta: [4]

### Pregunta 8:

Los archivos de extension `.feature`

1. Contienen los escenarios de prueba.
2. Contiene la configuración de protractor.
3. Contiene el código javascript de los pasos.
4. Es el fichero del Page Object.

> Respuesta: [1]

### Pregunta 9:

Depurar las pruebas nos permite:

1. Ejecutar los tests paso a paso.
2. Corregir cualquier error en las pruebas.
3. Ver dónde falla exactamente la aplicación.
4. Todas las anteriores.

> Respuesta: [4]

### Pregunta 10:

BDD significa:

1. Base desarrollo de comportamiento.
2. Desarrollo básico de driver.
3. Desarrollo guiado por comportamiento.
4. Ninguna las anteriores.

> Respuesta: [3]

### Pregunta 11:
El framework utilizado para implementar BDD es:

1. Cucumber
2. Jasmine
3. Gherkin
4. Protractor

> Respuesta: [1]

### Pregunta 12:
¿Qué es Gherkin?

1. Un lenguaje específico de Dominio.
2. Una herramienta de BDD.
3. Un framework de Cucumber.
4. Un lenguaje de programación.

> Respuesta: [1]

### Pregunta 13:
¿Qué nos describe la palabra clave `Feature` de Gherkin?

1. La descripción a alto nivel de una funcionalidad.
2. Un paso de un escenario.
3. La regla de una funcionalidad.
4. El resultado esperado tras una acción.

> Respuesta: [1]

### Pregunta 14:
Indique la afirmación correcta sobre la palabra clave `Rule`

1. Es una palabra opcional.
2. Representa una regla de negocio.
3. Agrupa escenarios que pertenecen a una misma regla de negocio.
4. Todas las anteriores.

> Respuesta: [4]

### Pregunta 15:
¿Cuántos pasos son recomendables por cada escenario?

1. Todos los que queramos.
2. Cuanto menos mejor.
3. De tres a cinco.
4. Es indiferente.

> Respuesta: [3]

### Pregunta 16:
`Given` representa:

1. Una acción sobre la UI.
2. Un resultado esperado.
3. Un requisito.
4. Una excepción.

Respuesta: [3]

### Pregunta 17:
`When` representa:

1. Una acción sobre la UI.
2. Un resultado esperado.
3. Un requisito.
4. Ninguna de las anteriores.

Respuesta: [1]

### Pregunta 18:
`Then` representa:

1. Una acción sobre la UI.
2. Un resultado esperado.
3. Un requisito.
4. Todas de las anteriores.

> Respuesta: [2] 

### Pregunta 19:
`And` representa:

1. Una acción sobre la UI.
2. Un resultado esperado.
3. Un requisito.
4. Lo mismo que el paso que le precede ya sea `When`, `Then`, etc...

> Respuesta: [4] 

### Pregunta 20
Background permite:

1. Es el backend de los escenarios.
2. Añadir contexto común a un conjunto de escenarios.
3. Es totalmente obligatorio.
4. No existe dicha palabra clave.

> Respuesta: [2]

### Pregunta 21
Scenario Outline

1. Ejecuta un escenario tantas veces como examples tenga.
2. Es el resumen de un escenario.
3. Permite ejecutar un escenario solo una vez.
4. Es una palabra clave incorrecta.

> Respuesta: [1]

### Pregunta 22
El siguiente escenario es correcto.

``` 
 Scenario: Abrir la web de angular https://angular.io/
    Given tenemos un usuario y contraseña correcta
    When el usuario abre la web de angular
    Then accedemos a nuestra cuenta de Openwebinars
```

1. Verdadero.
2. Faltan datos.
3. Falso.
4. Son pocos pasos para determinarlo.

> Respuesta: [1]

### Pregunta 23
¿Cuál de las siguientes afirmaciones es una ventaja de BDD?

1. Usa un lenguaje común que todos los miembros del equipo pueden entender.
2. Se pueden crear nuevos escenarios de prueba fácilmente y por parte de cualquier miembro del equipo.
3. Genera documentación.
4. Todas las anteriores.

> Respuesta: [4]

## Sección 3 - Caso práctico

### Pregunta 24
¿Cuál es el lenguaje de programación utilizado para los tests?

1. Java
2. Javascript.
3. Python
4. C++

> Respuesta: [2]

## Pregunta 25
¿Cuál de las siguientes afirmaciones acerca de Javascript es correcta?

1. Es un lenguaje de etiquetas como HTML.
2. Está totalmente relacionado con Java tal y como su propio nombre indica.
3. Es el lenguaje utilizado para interaccionar con la aplicación web en nuestras pruebas.
4. No es un lenguaje de programación.

> Respuesta: [3]

## Pregunta 26
¿Qué es un IDE?

1. Un soporte para ver la consola de las aplicaciones web.
2. Una herramienta para probar APIs.
3. Entorno de Desarrollo Integrado.
4. Interfaz de Escenario.

Respuesta: [3]

## Pregunta 27
El IDE utilizado en este curso es:

1. Webstorm.
2. IntelliJ.
3. Visual Studio.
4. Netbeans.

> Respuesta: [1]

### Pregunta 28
Las etiquetas:

1. Categorizan los escenarios.
2. Permiten ejecutar unos escenarios u otros según la etiqueta que contengan.
3. Puede haber tantas como queramos.
4. Todas las anteriores.

Respuesta: [4]

## Pregunta 29
¿Qué pasa si pedimos ejecutar escenarios que contienen una etiqueta que no existe?

1. Se ejecutan todos los tests.
2. No se ejecuta ningún test.
3. Se ejecutan aquellos tests (si existen) con una etiqueta parecida.
4. Ejecuta un escenario al azar.

Respuesta: [2]

### Pregunta 30
¿En qué navegador podemos ejecutar las pruebas?

1. Chrome.
2. Firefox.
3. Safari.
4. Todos los anteriores

> Respuesta: [4]

## Pregunta 31
¿Cuál de las siguientes opciones ejecuta los scenarios con la etiquera @happyPath?

1. `protractor protractor.conf.js --cucumber.tags=@happyPath`
2. `protractor.conf.js --cucumber.tags=@happyPath`
3. `protractor --cucumber.tags=@happyPath`
4. `protractor protractor.conf.js`

> Respuesta: [1]

## Pregunta 32
Para depurar las pruebas en Webstorm...

1. Podemos crear una configuración por cada navegador web.
2. Webstorm nos permite añadir distintas configuraciones.
3. Webstorm nos permite añadir los parámetros que necesitemos: navegador, etiquetas, etc...
4. Todas las anteriores.

> Respuesta: [4]

## Pregunta 33
Seleccione la opción que explica la funcionalidad del código adjunto.

```
clickButton: function(button, callback) {
      browser.wait(protractor.ExpectedConditions.elementToBeClickable(properties.homePage.button[button])).then(function() {
         properties.homePage.button[button].click()', properties.homePage.button[button]).then(function() {
            logger.info('Button ' + button + ' clicked');
            callback();
         });
      });
   },
```

1. Esperar a que un elemento sea clicable y clicar en él.
2. Hacer click en un botón sin esperar a nada.
3. Escribir algo en un elemento.
4. Ninguna de las anteriores.

> Respuesta: [3]

## Pregunta 34
Seleccione la opción que explica la funcionalidad del código adjunto.

```
methodProtractor: function(button, callback) {
      expect(properties.homePage.button[button].isEnabled()).to.be.eventually.equal(true).then(function() {
         logger.info('Button ' + button + ' is clickable');
         callback();
      });
   },
```

1. Comprueba si un botón está habilitado.
2. Espera 10 segundos a que termine un proceso.
3. Click en un botón.
4. Todas las anteriores.

> Respuesta: [1]

## Pregunta 35
Seleccione la opción que explica la funcionalidad del código adjunto.

```properties.homePage.product[product].personalInformation.firstName.sendKeys(firstName);```

1. Comprueba si un botón se puede pulsar.
2. Escribe el firstName en un elemento.
3. Comprueba la presencia de un elemento.
4. Abre un desplegable.

> Respuesta: [1]

## Pregunta 36
Seleccione la opción que explica la funcionalidad del código adjunto.

```
browser.wait(protractor.ExpectedConditions.visibilityOf(properties.homePage.messages.popUpConfirmation), 30000).then(function() {
         expect(properties.homePage.messages.popUpConfirmation.isPresent()).to.be.eventually.equal(true).then(function() {
            callback();
         });
      });
```

1. Selecciona un checkbox.
2. No hace ninguna comprobación
3. Comprueba si aparece un mensaje.
4. Selecciona una opción de un desplegable.

> Respuesta: [3]

## Pregunta 37
Seleccione la opción que explica la funcionalidad del código adjunto.

```logger.info('El desplegable: ' + dropdown + ' tiene el valor: ' + value);```

1. Imprime por la salida un mensaje informando del valor de un desplegable.
2. Es un mensaje de tipo WARN.
3. No se mostrará salvo que haya un error grave.
4. Nunca va a imprimir nada.

> Respuesta: [1]


## Pregunta 38
Seleccione la opción que explica la funcionalidad del código adjunto.

```
Scenario Outline: abrir una página de un producto y comprobar su url.
    Given user opens <product>  page
    Then <productUrl> section is opened

    Examples:
      | product | productUrl   |
      | CHF     | cash-high |
```

1. Abre una web y comprueba su url.
2. Abre una web y no comprueba su url.
3. No abre ninguna web.
4. Abre la web en chrome.

> Respuesta: [1]


## Pregunta 39
Seleccione la opción que explica la funcionalidad del código adjunto.

```
Scenario: Abrir la web de angular https://angular.io/
    When el usuario abre la web de angular
```

1. Abre una web de Angular.
2. Abre una web cualquiera.
3. No abre ninguna web.
4. Se ejecuta varias veces.

> Respuesta: [1]

## Pregunta 40
 Seleccione la opción que explica la funcionalidad del código adjunto.

```
When(/^click on (.*) button$/, function(button, callback) {
    homePage.clickButton(button, callback);
});
```

1. Define el paso del resultado esperado de hacer click en un botón y su método asociado.
2. Define el paso del requisito de hacer click en un botón y su método asociado.
3. Define el paso de la acción de hacer click en un botón y su método asociado.
4. Define una rule de una regla de negocio.

> Respuesta: [3]


