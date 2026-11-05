# Configurador de macropad CH57x (514c:8851)

Configurador web para los macropads chinos con chip CH57x de **3 teclas y 1 perilla**
(USB `514c:8851`, a veces vendidos como "MINI_KEYBOARD"). Funciona en el navegador con
[WebHID](https://developer.mozilla.org/docs/Web/API/WebHID_API): no hay que instalar nada.

## Uso

1. Abre la página en **Chrome o Edge** (Firefox y Safari no soportan WebHID).
2. Presiona **Conectar** y elige "USB Keyboard" en el diálogo del navegador.
3. Presiona **Respaldar (JSON)** para guardar la configuración actual antes de cambiar nada.
4. Elige una tecla o una acción de la perilla y asígnale:
   - una combinación o secuencia de teclas (con botón **Capturar**),
   - una acción multimedia (volumen, reproducir/pausa, brillo, calculadora…),
   - una acción de mouse (clics, rueda).
5. Presiona **Guardar cambios en el macropad**. La página vuelve a leer el dispositivo para
   verificar que se guardó.

La configuración queda en la memoria del macropad y funciona en cualquier computadora,
sin software.

## Privacidad y seguridad

- Es una página estática: no tiene servidor, no recolecta datos y no hace peticiones de red.
- Solo puede acceder al dispositivo que elijas en el diálogo del navegador, y solo busca
  dispositivos `514c:8851`.
- No modifica el firmware: solo cambia la asignación de teclas, que se puede volver a cambiar
  en cualquier momento.

## Limitaciones conocidas

- Probado en **una sola unidad** de 3 teclas + 1 perilla. Otros modelos con el mismo ID
  podrían tener otra distribución.
- En este modelo, los modificadores (Ctrl, Shift, Alt, Win) solo funcionan en la primera tecla
  de una secuencia.
- El macropad guarda 3 capas, pero no se sabe cómo activar las capas 2 y 3. Lo normal es usar
  solo la capa 1.
- La iluminación es experimental: los modos disponibles son apagada, fija, destello al
  presionar (dos variantes) y solo la tecla presionada, en 8 colores.

## Publicarlo

Es un solo archivo (`index.html`). WebHID requiere HTTPS, así que GitHub Pages funciona
directamente: *Settings → Pages → Deploy from a branch → `main` / root*.

## Créditos

El protocolo USB de este macropad fue documentado por la comunidad mediante ingeniería inversa:

- [kriomant/ch57x-keyboard-tool](https://github.com/kriomant/ch57x-keyboard-tool),
  © Mikhail Trishchenkov, licencia MIT / Apache-2.0
- [civcode/ch57x-keyboard-tool-cpp](https://github.com/civcode/ch57x-keyboard-tool-cpp),
  © civcode, licencia MIT

Este proyecto no está afiliado al fabricante.

## Licencia

[MIT](LICENSE)
