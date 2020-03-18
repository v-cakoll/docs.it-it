---
title: Debug delle impostazioni di configurazione della profilaturaDebugging profiling config settings
description: Informazioni sulle impostazioni di runtime che configurano il debug e la profilatura per le app .NET Core.Learn about run-time settings that configure debugging and profiling for .NET Core apps.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: c57cfa7233f48def890ded3c9d589b7f268147df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74802799"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a>Opzioni di configurazione in fase di esecuzione per il debug e la profilatura

## <a name="enable-diagnostics"></a>Abilitare la diagnostica

- Configura se il debugger, il profiler e la diagnostica EventPipe sono abilitati o disabilitati.
- Impostazione predefinita: Abilitato (`1`).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_EnableDiagnostics` | `1`- abilitato<br/>`0`- disabilitato |

## <a name="enable-profiling"></a>Abilita profilatura

- Configura se la profilatura è abilitata per il processo attualmente in esecuzione.
- Impostazione predefinita: Disabilitato (`0`).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variabile di ambiente** | `CORECLR_ENABLE_PROFILING` | `0`- disabilitato<br/>`1`- abilitato |

## <a name="profiler-guid"></a>Profiler GUID

- Specifica il GUID del profiler da caricare nel processo attualmente in esecuzione.

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variabile di ambiente** | `CORECLR_PROFILER` | *guid di stringa* |

## <a name="profiler-location"></a>Posizione del profiler

- Specifica il percorso della DLL del profiler da caricare nel processo attualmente in esecuzione (o processo a 32 bit o a 64 bit).
- Se è impostata più di una variabile, le variabili specifiche di bit hanno la precedenza. Specificano il numero di bit del profiler da caricare.
- Per ulteriori informazioni, vedere [Ricerca della libreria del profiler](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).

| | Nome impostazione | Valori |
| - | - | - |
| **Variabile di ambiente** | `CORECLR_PROFILER_PATH` | *percorso-stringa* |
| **Variabile di ambiente** | `CORECLR_PROFILER_PATH_32` | *percorso-stringa* |
| **Variabile di ambiente** | `CORECLR_PROFILER_PATH_64` | *percorso-stringa* |

## <a name="write-perf-map"></a>Scrivi mappa perf

- Abilita o disabilita la scrittura */tmp/perf-$pid.map* nei sistemi Linux.
- Impostazione predefinita: Disabilitato (`0`).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_PerfMapEnabled` | `0`- disabilitato<br/>`1`- abilitato |

## <a name="perf-log-markers"></a>Marcatori di log perf

- Quando `COMPlus_PerfMapEnabled` è `1`impostato su , abilita o disabilita l'accettato e l'ignorato del segnale specificato come marcatore nei registri perf.
- Impostazione predefinita: Disabilitato (`0`).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_PerfMapIgnoreSignal` | `0`- disabilitato<br/>`1`- abilitato |
