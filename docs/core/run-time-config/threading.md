---
title: Impostazioni di configurazione Threading
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il threading per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 1c7c16993a07ef95223481791153b75ab2f61533
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761928"
---
# <a name="run-time-configuration-options-for-threading"></a>Opzioni di configurazione in fase di esecuzione per il threading

## <a name="cpu-groups"></a>Gruppi CPU

- Configura se i thread vengono distribuiti automaticamente tra gruppi di CPU.
- Se si omette questa impostazione, i thread non verranno distribuiti tra gruppi di CPU. Equivale a impostare il valore su `0` .

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_Thread_UseAllCpuGroups` | `0`-disabilitato<br/>`1`-abilitato |

## <a name="minimum-threads"></a>Numero minimo di thread

- Specifica il numero minimo di thread per il pool di thread di lavoro.
- Corrisponde al <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> metodo.

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

- Specifica il numero massimo di thread per il pool di thread di lavoro.
- Corrisponde al <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> metodo.

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
