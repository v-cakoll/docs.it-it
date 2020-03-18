---
title: Impostazioni di configurazione del threading
description: Informazioni sulle impostazioni di runtime che configurano il threading per le app .NET Core.Learn about run-time settings that configure threading for .NET Core apps.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 68b8e93ca6ec3f708a7a627307655ada1955500a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789859"
---
# <a name="run-time-configuration-options-for-threading"></a>Opzioni di configurazione in fase di esecuzione per il threadingRun-time configuration options for threading

## <a name="cpu-groups"></a>Gruppi CPU

- Configura se i thread vengono distribuiti automaticamente tra i gruppi della CPU.
- Impostazione predefinita: Disabilitato (`0`).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_Thread_UseAllCpuGroups` | `0`- disabilitato<br/>`1`- abilitato |

## <a name="minimum-threads"></a>Numero minimo di thread

- Specifica il numero minimo di thread per il pool di thread di lavoro.
- Corrisponde al <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> metodo.

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MinThreads` | Un numero intero che rappresenta il numero minimo di thread |
| **MSBuild (proprietà)** | `ThreadPoolMinThreads` | Un numero intero che rappresenta il numero minimo di thread |
| **Variabile di ambiente** | N/D | N/D |

### <a name="examples"></a>Esempi

*runtimeconfig.json:*

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

- Specifica il numero massimo di thread per il pool di thread di lavoro.
- Corrisponde al <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> metodo.

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MaxThreads` | Un numero intero che rappresenta il numero massimo di thread |
| **MSBuild (proprietà)** | `ThreadPoolMaxThreads` | Un numero intero che rappresenta il numero massimo di thread |
| **Variabile di ambiente** | N/D | N/D |

### <a name="examples"></a>Esempi

*runtimeconfig.json:*

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
