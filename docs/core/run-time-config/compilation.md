---
title: Impostazioni di configurazione della compilazione
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il funzionamento del compilatore JIT per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bcc445b6edc48d9432ee614b0b19c9c25621f4a0
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802820"
---
# <a name="run-time-configuration-options-for-compilation"></a>Opzioni di configurazione della fase di esecuzione per la compilazione

## <a name="tiered-compilation"></a>Compilazione a livelli

- Configura se il compilatore JIT utilizza la [compilazione a livelli](../whats-new/dotnet-core-3-0.md#tiered-compilation).
- In .NET Core 3,0 e versioni successive la compilazione a più livelli è abilitata per impostazione predefinita.
- In .NET Core 2,1 e 2,2 la compilazione a più livelli è disabilitata per impostazione predefinita.

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `System.Runtime.TieredCompilation` | Abilitazione di `true`<br/>`false` disabilitato |
| **Variabile di ambiente** | `COMPlus_TieredCompilation` | Abilitazione di `1`<br/>`0` disabilitato |
