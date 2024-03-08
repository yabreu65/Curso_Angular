Paso a Paso: Pasar Información del Padre al Hijo en Angular
Paso 1: Crear una Propiedad en el Componente Hijo con @Input()
En el archivo del componente hijo (por ejemplo, hijo.component.ts), crea una propiedad decorada con @Input() para recibir datos del componente padre.

typescript
Copy code
// En hijo.component.ts
import { Component, Input } from '@angular/core';

@Component({
selector: 'app-hijo',
templateUrl: './hijo.component.html',
styleUrls: ['./hijo.component.css']
})
export class HijoComponent {
@Input() datosDelPadre: any;
}
Paso 2: Utilizar la Propiedad en el Componente Hijo
En el archivo HTML del componente hijo (por ejemplo, hijo.component.html), puedes utilizar la propiedad datosDelPadre como desees.

html
Copy code

<!-- En hijo.component.html -->
<p>Información del Padre: {{ datosDelPadre }}</p>
Paso 3: Vincular Datos en el Componente Padre
En el archivo del componente padre (por ejemplo, padre.component.ts), vincula los datos que deseas pasar al componente hijo.

typescript
Copy code
// En padre.component.ts
import { Component } from '@angular/core';

@Component({
selector: 'app-padre',
templateUrl: './padre.component.html',
styleUrls: ['./padre.component.css']
})
export class PadreComponent {
datosParaHijo = 'Datos importantes del padre';
}
Paso 4: Utilizar el Componente Hijo en el Componente Padre y Vincular los Datos
En el archivo HTML del componente padre (por ejemplo, padre.component.html), utiliza el componente hijo y vincula los datos utilizando la propiedad datosDelPadre.

html
Copy code

<!-- En padre.component.html -->

<app-hijo [datosDelPadre]="datosParaHijo"></app-hijo>
En este ejemplo, datosParaHijo se pasa al componente hijo utilizando la propiedad @Input() datosDelPadre que definiste en el paso 1.
