# PCB

Board layouts live in the EasyEDA Pro project `../easyeda/water-monitor.epro` (open it with EasyEDA Pro).

| PCB document | Preview | Notes |
|--------------|---------|-------|
| `ELIAS` | `pcb-elias-main-board.png` | Routed, top and bottom ground pours; linked to schematic `Medidor_de_Nivel_SMD` |
| `ELIAS_1` | `pcb-elias-1-partial-routing.png` | Partial routing, top-copper tracks only, no board outline |
| `NICO_` | `pcb-nico-ground-pour.png` | Routed, with ground pour |
| `NICO_SIN_PLANO_DE_TIERRA` | `pcb-nico-no-ground-plane.png` | Same routing as `NICO_`, without ground pour |
| `PCB12`, `PCB13` | none | Empty documents |

Previews are produced with `../../../_shared/easyeda_render.py` (`pro-pcb-routed`); they are renders of the project data, not Gerber output.
