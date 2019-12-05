---
title: Debug delle impostazioni di configurazione della profilatura
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il debug e la profilatura per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: c57cfa7233f48def890ded3c9d589b7f268147df
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802799"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a>Opzioni di configurazione in fase di esecuzione per il debug e la profilatura

## <a name="enable-diagnostics"></a>Abilitare la diagnostica

- Configura se il debugger, il profiler e la diagnostica EventPipe sono abilitati o disabilitati.
- Impostazione predefinita: abilitata (`1`).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_EnableDiagnostics` | Abilitazione di `1`<br/>`0` disabilitato |

## <a name="enable-profiling"></a>Abilita profilatura

- Configura se la profilatura è abilitata per il processo attualmente in esecuzione.
- Impostazione predefinita: disabilitato (`0`).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | N/D | N/D |
| **Variabile di ambiente** | `CORECLR_ENABLE_PROFILING` | `0` disabilitato<br/>Abilitazione di `1` |

## <a name="profiler-guid"></a>GUID Profiler

- Specifica il GUID del profiler da caricare nel processo attualmente in esecuzione.

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | N/D | N/D |
| **Variabile di ambiente** | `CORECLR_PROFILER` | *stringa-GUID* |

## <a name="profiler-location"></a>Percorso Profiler

- Specifica il percorso della DLL del profiler da caricare nel processo attualmente in esecuzione (o processo a 32 bit o a 64 bit).
- Se è impostata più di una variabile, le variabili specifiche di bit hanno la precedenza. Specificano il bit del profiler da caricare.
- Per ulteriori informazioni, vedere [ricerca della libreria del profiler](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).

| | Nome impostazione | Valori |
| - | - | - |
| **Variabile di ambiente** | `CORECLR_PROFILER_PATH` | *percorso stringa* |
| **Variabile di ambiente** | `CORECLR_PROFILER_PATH_32` | *percorso stringa* |
| **Variabile di ambiente** | `CORECLR_PROFILER_PATH_64` | *percorso stringa* |

## <a name="write-perf-map"></a>Mappa delle prestazioni di scrittura

- Abilita o Disabilita la scrittura */tmp/perf-$PID. map* nei sistemi Linux.
- Impostazione predefinita: disabilitato (`0`).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_PerfMapEnabled` | `0` disabilitato<br/>Abilitazione di `1` |

## <a name="perf-log-markers"></a>Marcatori log prestazioni

- Quando `COMPlus_PerfMapEnabled` è impostato su `1`, Abilita o Disabilita il segnale specificato da accettare e ignorare come marcatore nei log delle prestazioni.
- Impostazione predefinita: disabilitato (`0`).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_PerfMapIgnoreSignal` | `0` disabilitato<br/>Abilitazione di `1` |
