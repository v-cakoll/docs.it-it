---
title: Impostazioni di configurazione Threading
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il threading per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: ed7688d4d8f7178440fe59afc6e2f5e0a11b2a5c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733427"
---
# <a name="run-time-configuration-options-for-threading"></a>Opzioni di configurazione in fase di esecuzione per il threading

## <a name="cpu-groups"></a>Gruppi CPU

- Configura se i thread vengono distribuiti automaticamente tra gruppi di CPU.
- Impostazione predefinita: disabilitato (`0`).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_Thread_UseAllCpuGroups` | `0` disabilitato<br/>Abilitazione di `1` |

## <a name="minimum-threads"></a>Numero minimo di thread

- Specifica il numero minimo di thread per il ThreadPool del ruolo di lavoro.
- Corrisponde al metodo <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>.

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `System.Threading.ThreadPool.MinThreads` | Intero che rappresenta il numero minimo di thread |
| **MSBuild (proprietà)** | `ThreadPoolMinThreads` | Intero che rappresenta il numero minimo di thread |
| **Variabile di ambiente** | N/D | N/D |

### <a name="examples"></a>Esempi

file *runtimeconfig. JSON* :

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

File di progetto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a>Numero massimo di thread

- Specifica il numero massimo di thread per il ThreadPool di lavoro.
- Corrisponde al metodo <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `System.Threading.ThreadPool.MaxThreads` | Intero che rappresenta il numero massimo di thread |
| **MSBuild (proprietà)** | `ThreadPoolMaxThreads` | Intero che rappresenta il numero massimo di thread |
| **Variabile di ambiente** | N/D | N/D |

### <a name="examples"></a>Esempi

file *runtimeconfig. JSON* :

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

File di progetto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
