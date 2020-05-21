---
title: Impostazioni di configurazione della compilazione
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il funzionamento del compilatore JIT per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: cfcf9b5fc8d11a4ae35ab9b152f32133cd6930bf
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762006"
---
# <a name="run-time-configuration-options-for-compilation"></a>Opzioni di configurazione della fase di esecuzione per la compilazione

## <a name="tiered-compilation"></a>Compilazione a livelli

- Configura se il compilatore just-in-time (JIT) utilizza la [compilazione a livelli](../whats-new/dotnet-core-3-0.md#tiered-compilation). Metodi di transizione di compilazione a più livelli tramite due livelli:
  - Il primo livello genera il codice più rapidamente ([Quick JIT](#quick-jit)) o carica il codice precompilato ([ReadyToRun](#readytorun)).
  - Il secondo livello genera il codice ottimizzato in background ("Optimizing JIT").
- In .NET Core 3,0 e versioni successive la compilazione a più livelli è abilitata per impostazione predefinita.
- In .NET Core 2,1 e 2,2 la compilazione a più livelli è disabilitata per impostazione predefinita.
- Per ulteriori informazioni, vedere la [Guida alla compilazione](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md)a più livelli.

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `System.Runtime.TieredCompilation` | `true`-abilitato<br/>`false`-disabilitato |
| **MSBuild (proprietà)** | `TieredCompilation` | `true`-abilitato<br/>`false`-disabilitato |
| **Variabile di ambiente** | `COMPlus_TieredCompilation` | `1`-abilitato<br/>`0`-disabilitato |

### <a name="examples"></a>Esempi

file *runtimeconfig. JSON* :

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

## <a name="quick-jit"></a>JIT rapido

- Configura se il compilatore JIT utilizza *JIT rapido*. Per i metodi che non contengono cicli e per cui il codice precompilato non è disponibile, Quick JIT li compila più rapidamente ma senza ottimizzazioni.
- L'abilitazione di JIT rapido riduce il tempo di avvio ma può produrre codice con caratteristiche di prestazioni ridotte. Ad esempio, il codice può usare più spazio dello stack, allocare più memoria ed eseguire più lentamente.
- Se JIT è disabilitato ma la compilazione a più [livelli](#tiered-compilation) è abilitata, solo il codice precompilato partecipa alla compilazione a più livelli. Se un metodo non è precompilato con [ReadyToRun](#readytorun), il comportamento JIT è identico a quello in cui la [compilazione a livelli](#tiered-compilation) è stata disabilitata.
- In .NET Core 3,0 e versioni successive, Quick JIT è abilitato per impostazione predefinita.
- In .NET Core 2,1 e 2,2, Quick JIT è disabilitato per impostazione predefinita.

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `System.Runtime.TieredCompilation.QuickJit` | `true`-abilitato<br/>`false`-disabilitato |
| **MSBuild (proprietà)** | `TieredCompilationQuickJit` | `true`-abilitato<br/>`false`-disabilitato |
| **Variabile di ambiente** | `COMPlus_TC_QuickJit` | `1`-abilitato<br/>`0`-disabilitato |

### <a name="examples"></a>Esempi

file *runtimeconfig. JSON* :

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

## <a name="quick-jit-for-loops"></a>JIT rapido per i cicli

- Configura se il compilatore JIT USA Quick JIT sui metodi che contengono cicli.
- L'abilitazione di Quick JIT for loops può migliorare le prestazioni di avvio. Tuttavia, i cicli con esecuzione prolungata possono rimanere bloccati nel codice meno ottimizzato per lunghi periodi di tempo.
- Se [JIT rapido](#quick-jit) è disabilitato, questa impostazione non ha alcun effetto.
- Se si omette questa impostazione, Quick JIT non viene usato per i metodi che contengono cicli. Equivale a impostare il valore su `false` .

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `System.Runtime.TieredCompilation.QuickJitForLoops` | `false`-disabilitato<br/>`true`-abilitato |
| **MSBuild (proprietà)** | `TieredCompilationQuickJitForLoops` | `false`-disabilitato<br/>`true`-abilitato |
| **Variabile di ambiente** | `COMPlus_TC_QuickJitForLoops` | `0`-disabilitato<br/>`1`-abilitato |

### <a name="examples"></a>Esempi

file *runtimeconfig. JSON* :

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
    <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a>ReadyToRun

- Configura se il runtime di .NET Core usa codice precompilato per le immagini con i dati ReadyToRun disponibili. La disabilitazione di questa opzione impone al runtime il codice del Framework per la compilazione JIT.
- Per ulteriori informazioni, vedere [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).
- Se si omette questa impostazione, .NET utilizzerà i dati ReadyToRun quando sarà disponibile. Equivale a impostare il valore su `1` .

| | Nome impostazione | Valori |
| - | - | - |
| **Variabile di ambiente** | `COMPlus_ReadyToRun` | `1`-abilitato<br/>`0`-disabilitato |
