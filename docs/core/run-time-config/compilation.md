---
title: Impostazioni di configurazione compilazione
description: Informazioni sulle impostazioni di runtime che configurano il funzionamento del compilatore JIT per le app .NET Core.Learn about run-time settings that configure how the JIT compiler works for .NET Core apps.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: ac51aa13254b2f2b1fdd8d1dd9c52559831a1659
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989116"
---
# <a name="run-time-configuration-options-for-compilation"></a>Opzioni di configurazione in fase di esecuzione per la compilazioneRun-time configuration options for compilation

## <a name="tiered-compilation"></a>Compilazione a livelli

- Configura se il compilatore JIT (Just-In-Time) utilizza la [compilazione a livelli.](../whats-new/dotnet-core-3-0.md#tiered-compilation) Metodi di transizione di compilazione a livelli tramite due livelli:Tiered compilation transitions methods through two tiers:
  - Il primo livello genera codice più rapidamente ([JIT rapido](#quick-jit)) o carica codice precompilato ([ReadyToRun](#readytorun)).
  - Il secondo livello genera codice ottimizzato in background ("ottimizzazione di JIT").
- In .NET Core 3.0 e versioni successive, la compilazione a livelli è abilitata per impostazione predefinita.
- In .NET Core 2.1 e 2.2 la compilazione a livelli è disabilitata per impostazione predefinita.
- Per ulteriori informazioni, vedere la guida alla [compilazione a livelli](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation` | `true`- abilitato<br/>`false`- disabilitato |
| **MSBuild (proprietà)** | `TieredCompilation` | `true`- abilitato<br/>`false`- disabilitato |
| **Variabile di ambiente** | `COMPlus_TieredCompilation` | `1`- abilitato<br/>`0`- disabilitato |

### <a name="examples"></a>Esempi

*runtimeconfig.json:*

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

File di progetto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a>JIT veloce

- Configura se il compilatore JIT utilizza *JIT rapido*. Per i metodi che non contengono cicli e per i quali il codice precompilato non è disponibile, JIT rapido li compila più rapidamente ma senza ottimizzazioni.
- L'abilitazione rapida di JIT riduce il tempo di avvio ma può produrre codice con caratteristiche di prestazioni ridotte. Ad esempio, il codice può utilizzare più spazio dello stack, allocare più memoria ed eseguire più lentamente.
- Se JIT rapido è disabilitato ma [la compilazione a più livelli](#tiered-compilation) è abilitata, solo il codice precompilato partecipa alla compilazione a livelli. Se un metodo non è precompilato con [ReadyToRun](#readytorun), il comportamento JIT è lo stesso di se la compilazione a più livelli fosse [disabilitata.](#tiered-compilation)
- In .NET Core 3.0 e versioni successive, JIT rapido è abilitato per impostazione predefinita.
- In .NET Core 2.1 e 2.2, JIT rapido è disabilitato per impostazione predefinita.

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation.QuickJit` | `true`- abilitato<br/>`false`- disabilitato |
| **MSBuild (proprietà)** | `TieredCompilationQuickJit` | `true`- abilitato<br/>`false`- disabilitato |
| **Variabile di ambiente** | `COMPlus_TC_QuickJit` | `1`- abilitato<br/>`0`- disabilitato |

### <a name="examples"></a>Esempi

*runtimeconfig.json:*

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

File di progetto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a>JIT rapido per i loop

- Configura se il compilatore JIT utilizza JIT rapido su metodi che contengono cicli.
- L'abilitazione rapida di JIT per i cicli può migliorare le prestazioni di avvio. Tuttavia, i cicli a esecuzione prolungata possono rimanere bloccati nel codice meno ottimizzato per lunghi periodi.
- Se [Quick JIT](#quick-jit) è disabilitato, questa impostazione non ha alcun effetto.
- Impostazione predefinita: Disabilitato (`false`).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation.QuickJitForLoops` | `false`- disabilitato<br/>`true`- abilitato |
| **MSBuild (proprietà)** | `TieredCompilationQuickJitForLoops` | `false`- disabilitato<br/>`true`- abilitato |
| **Variabile di ambiente** | `COMPlus_TC_QuickJitForLoops` | `0`- disabilitato<br/>`1`- abilitato |

### <a name="examples"></a>Esempi

*runtimeconfig.json:*

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

File di progetto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>false</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a>ReadyToRun

- Configura se il runtime di .NET Core utilizza codice precompilato per le immagini con i dati ReadyToRun disponibili. La disabilitazione di questa opzione forza il runtime a compilare il codice del framework JIT.
- Per ulteriori informazioni, vedere [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).
- Impostazione predefinita: Abilitato (`1`).

| | Nome impostazione | Valori |
| - | - | - |
| **Variabile di ambiente** | `COMPlus_ReadyToRun` | `1`- abilitato<br/>`0`- disabilitato |
