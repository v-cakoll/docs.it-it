---
title: Impostazioni di configurazione Threading
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il threading per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6a920dbc301830e3f4c95bf637ff3de6d4f464ff
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802764"
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
| **Variabile di ambiente** | N/D | N/D |

## <a name="maximum-threads"></a>Numero massimo di thread

- Specifica il numero massimo di thread per il ThreadPool di lavoro.
- Corrisponde al metodo <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `System.Threading.ThreadPool.MaxThreads` | Intero che rappresenta il numero massimo di thread |
| **Variabile di ambiente** | N/D | N/D |
