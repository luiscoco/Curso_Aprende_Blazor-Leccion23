# CURSO: APRENDE BLAZOR

# LECCIÓN 23: Cómo se configura el enrutamiento en una aplicación Blazor

**NOTA**: El video youtube de esta Lección23 está disponible en el siguiente vínculo: 


1. Abrir la aplicación Blazor con Visual Studio 2022

2. ```<Router AppAssembly="typeof(Program).Assembly">```

   ```<Router>```: componente de Blazor que habilita el enrutamiento dentro de la aplicación y cómo la aplicación responde (qué componente renderizar) cuando el usuario elige una nueva ruta. 

   ```AppAssembly="typeof(Program).Assembly```: indica al enrutador qué ensamblado contiene los componentes para enrutamiento. 

3. ```<Found Context="routeData">```

   ```<Found>```: se ejecuta cuando se encuentra una ruta que coincide con la URL actual. 

   ```Context="routeData"```: la variable (routeData) almacena los datos relacionados con la ruta encontrada. 

4. ```<RouteView RouteData="routeData" DefaultLayout="typeof(Layout.MainLayout)" />```

   ```<RouteView>```: componente que renderiza la página o componente correspondiente a la ruta encontrada. Utiliza ```RouteData``` para identificar qué componente se debe mostrar.

    ```RouteData="routeData"```: pasa la información de la ruta desde el ```Context``` del bloque ```<Found>``` al ```<RouteView>```, para renderizar el componente correcto.

    ```DefaultLayout="typeof(Layout.MainLayout)```: diseño por defecto que se utilizará al renderizar el componente enrutado.

5. ```<FocusOnNavigate RouteData="routeData" Selector="h1" />```

   ```<FocusOnNavigate>```: Este componente se utiliza para mejorar la accesibilidad gestionando el enfoque al navegar. 

       Cuando cambia la ruta, se enfocará un elemento específico en la página recién renderizada.

    ```RouteData="routeData```: Esto vincula el componente a routeData, de modo que el comportamiento de enfoque esté ligado a la ruta encontrada.

    ```Selector="h1"```: Este es un selector CSS utilizado para identificar qué elemento debe ser enfocado cuando ocurre la navegación. 

       En este caso, selecciona el primer elemento ```<h1>``` de la nueva página y mueve el enfoque allí. 

       Esto es útil para la accesibilidad, asegurando que los lectores de pantalla y los usuarios de teclado sepan que el contenido ha cambiado después de la navegación.

## Resumen:

El componente <Router> habilita la navegación entre diferentes componentes en la aplicación Blazor.

Cuando se encuentra una ruta que coincide, el componente ```<RouteView>``` renderiza la página correspondiente dentro del MainLayout.

El componente ```<FocusOnNavigate>``` asegura que, después de la navegación, el enfoque se establezca en el primer elemento ```<h1>```, mejorando la accesibilidad para usuarios que navegan con teclado o lectores de pantalla.

Esta estructura de enrutamiento proporciona navegación y gestión de diseño mientras mejora la accesibilidad para los usuarios que navegan con teclado o dispositivos de asistencia.
