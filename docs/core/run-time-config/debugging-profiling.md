---
title: Debug delle impostazioni di configurazione della profilatura
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il debug e la profilatura per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 5efd0f776da4b7ce6ff7f3bdfda24feec6e00f79
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761993"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a>Opzioni di configurazione in fase di esecuzione per il debug e la profilatura

## <a name="enable-diagnostics"></a>Abilitare la diagnostica

- Configura se il debugger, il profiler e la diagnostica EventPipe sono abilitati o disabilitati.
- Se si omette questa impostazione, la diagnostica è abilitata. Equivale a impostare il valore su `1` .

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_EnableDiagnostics` | `1`-abilitato<br/>`0`-disabilitato |

## <a name="enable-profiling"></a>Abilita profilatura

- Configura se la profilatura è abilitata per il processo attualmente in esecuzione.
- Se si omette questa impostazione, la profilatura è disabilitata. Equivale a impostare il valore su `0` .

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | N/D | N/D |
| **Variabile di ambiente** | `CORECLR_ENABLE_PROFILING` | `0`-disabilitato<br/>`1`-abilitato |

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
- Se si omette questa impostazione, la scrittura della mappa delle prestazioni è disabilitata. Equivale a impostare il valore su `0` .

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_PerfMapEnabled` | `0`-disabilitato<br/>`1`-abilitato |

## <a name="perf-log-markers"></a>Marcatori log prestazioni

- Abilita o Disabilita il segnale specificato da accettare e ignorare come marcatore nei log delle prestazioni.
- Se si omette questa impostazione, il segnale specificato non verrà ignorato. Equivale a impostare il valore su `0` .

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_PerfMapIgnoreSignal` | `0`-disabilitato<br/>`1`-abilitato |

> [!NOTE]
> Questa impostazione viene ignorata se [COMPlus_PerfMapEnabled](#write-perf-map) viene omesso o impostato su `0` (ovvero disabilitato).
