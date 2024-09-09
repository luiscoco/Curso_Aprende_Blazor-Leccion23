# CURSO: APRENDE BLAZOR

# LECCIÓN 23: Cómo se configura el enrutamiento en una aplicación Blazor

**NOTA**: El video youtube de esta Lección23 está disponible en el siguiente vínculo: 


1. Abrir la aplicación Blazor con Visual Studio 2022

2. **<Router AppAssembly="typeof(Program).Assembly">**

**<Router>**: Este es el componente principal de Blazor que habilita el enrutamiento dentro de la aplicación. Determina cómo la aplicación responde a los cambios en la URL y qué componentes debe renderizar.

**AppAssembly="typeof(Program).Assembly**: La propiedad AppAssembly indica al enrutador qué ensamblado contiene los componentes que deben usarse para el enrutamiento. 

En este caso, se especifica el ensamblado donde se define la clase Program (el punto de entrada de la aplicación Blazor), que normalmente es el ensamblado principal del proyecto.

3. **<Found Context="routeData">**

**<Found>**: Este bloque se ejecuta cuando se encuentra una ruta que coincide con la URL actual. 

Cuando se encuentra la ruta, Blazor pasa la información de la ruta (contenida en routeData) a los componentes hijos.

**Context="routeData"**: El atributo Context asigna una variable local (routeData) para almacenar los datos relacionados con la ruta encontrada. 

Estos datos luego se utilizan en los componentes hijos, como <RouteView>.

4. **<RouteView RouteData="routeData" DefaultLayout="typeof(Layout.MainLayout)" />**

**<RouteView>**: Este componente es responsable de renderizar la página o componente correspondiente a la ruta encontrada. Utiliza RouteData para identificar qué componente se debe mostrar.

**RouteData="routeData"**: Esto pasa la información de la ruta desde el Context del bloque <Found> al <RouteView>, de manera que se pueda renderizar el componente correcto.

**DefaultLayout="typeof(Layout.MainLayout)**: Esto especifica el diseño por defecto que se utilizará al renderizar el componente enrutado. En este caso, MainLayout del espacio de nombres Layout se utilizará como diseño predeterminado para cualquier ruta que no especifique explícitamente un diseño diferente.

5. **<FocusOnNavigate RouteData="routeData" Selector="h1" />**

**<FocusOnNavigate>**: Este componente se utiliza para mejorar la accesibilidad gestionando el enfoque al navegar. Cuando cambia la ruta, se enfocará un elemento específico en la página recién renderizada.

**RouteData="routeData**: Esto vincula el componente a routeData, de modo que el comportamiento de enfoque esté ligado a la ruta encontrada.

**Selector="h1"**: Este es un selector CSS utilizado para identificar qué elemento debe ser enfocado cuando ocurre la navegación. En este caso, selecciona el primer elemento <h1> de la nueva página y mueve el enfoque allí. Esto es útil para la accesibilidad, asegurando que los lectores de pantalla y los usuarios de teclado sepan que el contenido ha cambiado después de la navegación.

## Resumen:

El componente <Router> habilita la navegación entre diferentes componentes en la aplicación Blazor.

Cuando se encuentra una ruta que coincide, el componente <RouteView> renderiza la página correspondiente dentro del MainLayout.

El componente <FocusOnNavigate> asegura que, después de la navegación, el enfoque se establezca en el primer elemento <h1>, mejorando la accesibilidad para usuarios que navegan con teclado o lectores de pantalla.

Esta estructura de enrutamiento proporciona navegación y gestión de diseño mientras mejora la accesibilidad para los usuarios que navegan con teclado o dispositivos de asistencia.
