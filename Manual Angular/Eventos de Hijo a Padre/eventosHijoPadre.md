# Paso a Paso: Pasar Eventos del Hijo al Padre en Angular

# Paso 1: Importar EventEmitter y Output en el Componente Hijo

```typescript
// En el archivo hijo.component.ts
import { EventEmitter, Output } from '@angular/core';
Paso 2: Crear un EventEmitter en el Componente Hijo
typescript
Copy code
// En el archivo hijo.component.ts
export class HijoComponent {
  @Output() onDeleteCharacter = new EventEmitter<string>();
}
Paso 3: Definir una Función en el Componente Hijo para Activar el Evento
typescript
Copy code
// En el archivo hijo.component.ts
export class HijoComponent {
  @Output() onDeleteCharacter = new EventEmitter<string>();

  deleteCharacter() {
    const data = 'Datos relevantes del evento desde el hijo';
    this.onDeleteCharacter.emit(data);
  }
}
Paso 4: Invocar la Función en el HTML del Componente Hijo
html
Copy code
<!-- En el archivo hijo.component.html -->
<button (click)="deleteCharacter()">Eliminar Personaje</button>
Paso 5: Vincular el Evento en el Componente Padre
html
Copy code
<!-- En el archivo padre.component.html -->
<app-hijo (onDeleteCharacter)="handleDeleteCharacter($event)"></app-hijo>
Paso 6: Implementar la Función en el Componente Padre
typescript
Copy code
// En el archivo padre.component.ts
export class PadreComponent {
  handleDeleteCharacter(data: string) {
    // Acciones en respuesta al evento recibido desde el hijo
    console.log('Evento recibido en el padre con datos:', data);
  }
}
```
