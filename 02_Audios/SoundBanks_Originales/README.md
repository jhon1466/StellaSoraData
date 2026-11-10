# Bancos de Sonido Originales (.bnk) y Mapeos de Eventos (AVG)

Esta carpeta contiene los archivos de banco de sonido Wwise originales (**`.bnk`**) del juego **Stella Sora**, junto con las tablas de mapeo que vinculan los **nombres de eventos / estados del juego** (por ejemplo: `M54`, `SE_092`, `UI_DIALOG_CLICK`) con los **archivos de audio WAV** almacenados en el repositorio.

---

## Archivos Incluidos

### 1. Bancos de Sonido Originales Wwise
* **`AVG.bnk`**: Banco original de efectos de sonido del modo historia / novela visual (AVG).
* **`Music_AVG.bnk`**: Banco original de pistas musicales asociadas a las escenas de historia.
* **`UI_AVG.bnk`**: Banco de sonidos de interfaz de usuario del sistema AVG.
* **`Init.bnk`**: Banco maestro de inicialización de Wwise (necesario para resolver buses, estados y jerarquías).
* **`Wwise_IDs.h`**: Encabezado C++ generado por Wwise con los 7,653 identificadores y hashes oficiales de Audiokinetic.

### 2. Tablas de Mapeo
* **Musica (`Music_AVG`)**:
  * [`Mapeo_Musica_AVG.json`](Mapeo_Musica_AVG.json): Mapeo estructurado en JSON de 158 pistas musicales (`M1` a `M150+`).
  * [`Mapeo_Musica_AVG.txt`](Mapeo_Musica_AVG.txt): Tabla de texto lista para consulta o scripts.
* **Efectos de Sonido (`AVG`)**:
  * [`Mapeo_Efectos_AVG.json`](Mapeo_Efectos_AVG.json): Mapeo estructurado en JSON de 594 efectos de sonido (`SE_001` a `SE_425`, etc.).
  * [`Mapeo_Efectos_AVG.txt`](Mapeo_Efectos_AVG.txt): Tabla de texto con cada evento y su archivo `AVG_*.wav` correspondiente.
* **Interfaz de Usuario (`UI_AVG`)**:
  * [`Mapeo_UI_AVG.json`](Mapeo_UI_AVG.json): Mapeo en JSON de sonidos de interfaz.
  * [`Mapeo_UI_AVG.txt`](Mapeo_UI_AVG.txt): Tabla de texto para sonidos de interfaz.

---

## Ejemplos Rapidos de Correspondencia

| Nombre en el Juego | Tipo | Archivo en Repositorio | ID WEM |
| :--- | :--- | :--- | :--- |
| **`M54`** | Musica / BGM | `02_Audios/Musica_y_Streams/162916245.wav` | `162916245` |
| **`SE_092`** | Efecto de Sonido | `02_Audios/SoundBanks_Desempaquetados/Efectos_y_Ambiente/AVG/AVG_333935801.wav` | `333935801` |
| **`SE_001`** | Efecto de Sonido | `02_Audios/SoundBanks_Desempaquetados/Efectos_y_Ambiente/AVG/AVG_602311911.wav` | `602311911` |
| **`UI_AVG_APP_MENU`** | UI | `02_Audios/SoundBanks_Desempaquetados/Efectos_y_Ambiente/UI_AVG/UI_AVG_102427698.wav` | `102427698` |
| **`UI_AVG_CHARINFO`** | UI | `02_Audios/SoundBanks_Desempaquetados/Efectos_y_Ambiente/UI_AVG/UI_AVG_885478236.wav` | `885478236` |

---

## Como Usar con wwiser

Para abrir e inspeccionar estos bancos de sonido en [wwiser](https://github.com/bnnm/wwiser):

```bash
# 1. Cargar junto con Init.bnk para resolver la jerarquia completa
python wwiser.py Init.bnk Music_AVG.bnk -v

# 2. Generar listas de reproduccion TXTP con nombres de eventos
python wwiser.py Init.bnk AVG.bnk -g
```
