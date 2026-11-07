<p align="center"><img src="docs/img/banner.svg" width="100%" alt="Groundwater Monitor: PCB Redesign"></p>

<p align="center"><img src="https://img.shields.io/badge/Year-2025-555"> <img src="https://img.shields.io/badge/EasyEDA-Pro-informational"> <img src="https://img.shields.io/badge/PCB-redesign-1f6feb"> <img src="https://img.shields.io/badge/ESP32-DevKitC-e7352c"> <img src="https://img.shields.io/badge/PSoC-5LP-1f6feb"> <img src="https://img.shields.io/badge/License-MIT-lightgrey"></p>
<p align="center"><a href="#english">English</a> · <a href="#español">Español</a></p>

## English

### Overview
PCB redesign of an autonomous IoT groundwater-level and water-conductivity monitor developed by **Nicolás Escurra** (advisor: **Enrique A. Vargas Cabral, PhD**, FCT – Universidad Católica "Nuestra Señora de la Asunción"). **Elías's contribution** is the redesigned carrier/main boards in EasyEDA Pro, done at the advisor's request. The monitor itself (its firmware and measurement method) is not part of this repository.

<p align="center"><img src="docs/img/field-enclosure.jpg" width="640" alt="Field enclosure of the groundwater monitor"><br><sub>Field enclosure of the monitor (2025)</sub></p>

### What the board connects
Taken from the parts and net names of the EasyEDA schematic (`Medidor_de_Nivel_SMD`):

| Item | Role on the board |
|------|-------------------|
| ESP32-DevKitC | Mounted on the carrier headers |
| CY8CKIT-059 (PSoC 5LP) | Mounted on the carrier headers |
| LM7805D2TRG | 5 V regulator fed from the 12 V input |
| Bidirectional level converter | Interface between the 3.3 V and 5 V domains |
| `TDS_DATA` | Input for the TDS (conductivity) sensor module |
| `DS18B20_DATA` | Input for the DS18B20 temperature sensor |
| `BAT_LEVEL` | Battery-level sense line |
| `PIN_WAKEUP` | Wake-up line |
| Screw terminals and headers | Field wiring (12 V, GND, sensor and signal connectors) |

### PCB renders
Previews generated from the EasyEDA Pro `.epcb` files with a small Python renderer: board outline, top (red) and bottom (blue) copper, vias, pads, copper pours and top silkscreen. They are not CAM-accurate Gerber output.

<table><tr>
<td align="center" width="50%"><img src="hardware/pcb/pcb-elias-main-board.png" width="440" alt="Board ELIAS, routed, with top and bottom ground pours"><br><sub><b>ELIAS</b>: routed two-layer board with top and bottom ground pours</sub></td>
<td align="center" width="50%"><img src="hardware/pcb/pcb-elias-1-partial-routing.png" width="440" alt="Board ELIAS_1, partial top-layer routing"><br><sub><b>ELIAS_1</b>: partially routed variant (top-copper tracks only, no board outline in the file)</sub></td>
</tr><tr>
<td align="center" width="50%"><img src="hardware/pcb/pcb-nico-ground-pour.png" width="440" alt="Board NICO_, routed, with ground pour"><br><sub><b>NICO_</b>: routed layout with ground pour</sub></td>
<td align="center" width="50%"><img src="hardware/pcb/pcb-nico-no-ground-plane.png" width="440" alt="Board NICO_SIN_PLANO_DE_TIERRA, routed, without ground pour"><br><sub><b>NICO_SIN_PLANO_DE_TIERRA</b>: same routing as NICO_, without the ground pour</sub></td>
</tr></table>

The project files do not record which layout came first, so the boards are captioned by their names in the file.

### Repository layout
```
hardware/
  easyeda/water-monitor.epro   EasyEDA Pro project (3 schematics, 6 PCB documents)
  pcb/                         Rendered board previews and board list
docs/img/                      Banner, field-enclosure photo and assembly photos
```
Open `hardware/easyeda/water-monitor.epro` with EasyEDA Pro to inspect the schematics and boards.

### Field photos
<table><tr>

</tr></table>

### Credits
- **Groundwater monitor** (concept, firmware and measurement method): developed by **Nicolás Escurra**, advised by **Enrique A. Vargas Cabral, PhD** (FCT – Universidad Católica "Nuestra Señora de la Asunción").
- **PCB redesign** (carrier/main boards in EasyEDA Pro): **Elías Álvarez**, at the advisor's request. Elías did not work on the monitor's code.

### License
MIT, see [LICENSE](LICENSE).

---

## Español

### Descripción general
Rediseño de PCB de un monitor IoT autónomo de nivel freático y conductividad del agua, desarrollado por **Nicolás Escurra** (asesor: **Enrique A. Vargas Cabral, PhD**, FCT, Universidad Católica "Nuestra Señora de la Asunción"). **La contribución de Elías** son las placas portadora/principal rediseñadas en EasyEDA Pro, realizadas a pedido del asesor. El monitor en sí (su firmware y método de medición) no forma parte de este repositorio.

<p align="center"><img src="docs/img/field-enclosure.jpg" width="640" alt="Gabinete de campo del monitor de aguas subterráneas"><br><sub>Gabinete de campo del monitor (2025)</sub></p>

### Qué conecta la placa
Según las piezas y los nombres de red del esquemático de EasyEDA (`Medidor_de_Nivel_SMD`):

| Elemento | Función en la placa |
|------|-------------------|
| ESP32-DevKitC | Montado sobre los cabezales de la placa portadora |
| CY8CKIT-059 (PSoC 5LP) | Montado sobre los cabezales de la placa portadora |
| LM7805D2TRG | Regulador de 5 V alimentado desde la entrada de 12 V |
| Conversor bidireccional de niveles | Interfaz entre los dominios de 3,3 V y 5 V |
| `TDS_DATA` | Entrada para el módulo sensor TDS (conductividad) |
| `DS18B20_DATA` | Entrada para el sensor de temperatura DS18B20 |
| `BAT_LEVEL` | Línea de medición del nivel de batería |
| `PIN_WAKEUP` | Línea de activación |
| Bornes y cabezales | Cableado de campo (12 V, GND, conectores de sensores y señales) |

### Renders de PCB
Vistas previas generadas desde los archivos `.epcb` de EasyEDA Pro mediante un pequeño renderizador en Python: contorno de placa, cobre superior (rojo) e inferior (azul), vías, pads, vertidos de cobre y serigrafía superior. No son salidas Gerber con precisión CAM.

<table><tr>
<td align="center" width="50%"><img src="hardware/pcb/pcb-elias-main-board.png" width="440" alt="Placa ELIAS, ruteada, con planos de masa superior e inferior"><br><sub><b>ELIAS</b>: placa ruteada de dos capas con planos de masa superior e inferior</sub></td>
<td align="center" width="50%"><img src="hardware/pcb/pcb-elias-1-partial-routing.png" width="440" alt="Placa ELIAS_1, ruteo parcial de la capa superior"><br><sub><b>ELIAS_1</b>: variante parcialmente ruteada (solo pistas de cobre superior, sin contorno de placa en el archivo)</sub></td>
</tr><tr>
<td align="center" width="50%"><img src="hardware/pcb/pcb-nico-ground-pour.png" width="440" alt="Placa NICO_, ruteada, con plano de masa"><br><sub><b>NICO_</b>: layout ruteado con plano de masa</sub></td>
<td align="center" width="50%"><img src="hardware/pcb/pcb-nico-no-ground-plane.png" width="440" alt="Placa NICO_SIN_PLANO_DE_TIERRA, ruteada, sin plano de masa"><br><sub><b>NICO_SIN_PLANO_DE_TIERRA</b>: mismo ruteo que NICO_, sin el plano de masa</sub></td>
</tr></table>

Los archivos del proyecto no registran qué layout se creó primero, por lo que las placas se describen según sus nombres en el archivo.

### Estructura del repositorio
```
hardware/
  easyeda/water-monitor.epro   Proyecto EasyEDA Pro (3 esquemáticos, 6 documentos PCB)
  pcb/                         Vistas previas renderizadas y lista de placas
docs/img/                      Banner, foto del gabinete de campo y fotos del montaje
```
Abrir `hardware/easyeda/water-monitor.epro` con EasyEDA Pro para inspeccionar los esquemáticos y las placas.

### Fotos de campo
<table><tr>

</tr></table>

### Créditos
- **Monitor de aguas subterráneas** (concepto, firmware y método de medición): desarrollado por **Nicolás Escurra**, con asesoría de **Enrique A. Vargas Cabral, PhD** (FCT, Universidad Católica "Nuestra Señora de la Asunción").
- **Rediseño de PCB** (placas portadora/principal en EasyEDA Pro): **Elías Álvarez**, a pedido del asesor. Elías no trabajó en el código del monitor.

### Licencia
MIT, ver [LICENSE](LICENSE).
