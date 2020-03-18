---
title: Impostazioni di configurazione della globalizzazione
description: Informazioni sulle impostazioni di runtime che configurano gli aspetti di globalizzazione di un'app .NET Core, ad esempio la modalità di analisi delle date in giapponese.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 3764d0eb714c094b44ae843a1e626073ff8d82e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76733462"
---
# <a name="run-time-configuration-options-for-globalization"></a>Opzioni di configurazione in fase di esecuzione per la globalizzazione

## <a name="invariant-mode"></a>Modalità invariante

- Determina se un'app .NET Core viene eseguita in modalità invariante di globalizzazione senza accedere ai dati e al comportamento specifici delle impostazioni cultura o se ha accesso ai dati culturali.
- Impostazione predefinita: eseguire l'app`false`con accesso ai dati culturali ( ).
- Per ulteriori informazioni, vedere [Modalità invariante di globalizzazione di .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | `System.Globalization.Invariant` | `false`- accesso ai dati culturali<br/>`true`- eseguire in modalità invariante |
| **MSBuild (proprietà)** | `InvariantGlobalization` | `false`- accesso ai dati culturali<br/>`true`- eseguire in modalità invariante |
| **Variabile di ambiente** | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | `0`- accesso ai dati culturali<br/>`1`- eseguire in modalità invariante |

### <a name="examples"></a>Esempi

*runtimeconfig.json:*

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

File di progetto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a>Intervalli dell'anno era

- Determina se i controlli dell'intervallo per i calendari che supportano più <xref:System.ArgumentOutOfRangeException>ere sono rilassati o se le date che causano un overflow nell'intervallo di date di un'era generano un' .
- Impostazione predefinita: i`false`controlli di intervallo sono rilassati ( ).
- Per ulteriori informazioni, vedere [Calendari, ere e intervalli di date: Controlli intervallo rilassato](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | `false`- rilassati controlli a distanza<br/>`true`- Gli overflow causano un'eccezione- overflow strame an exception |
| **Variabile di ambiente** | N/D | N/D |

## <a name="japanese-date-parsing"></a>Analisi data giapponese

- Determina se una stringa che contiene "1" o "Gannen" come l'anno viene analizzato correttamente o se è supportato solo "1".
- Impostazione predefinita: analizza le stringhe che contengono "1"`false`o "Gannen" come anno ( ).
- Per ulteriori informazioni, consultate [Rappresentare le date nei calendari con più ere.](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | `false`- "Gannen" o "1" è supportato<br/>`true`- è supportato solo "1" |
| **Variabile di ambiente** | N/D | N/D |

## <a name="japanese-year-format"></a>Formato anno giapponese

- Determina se il primo anno di un'era del calendario giapponese viene formattato come "Gannen" o come numero.
- Impostazione predefinita: formattare il primo anno`false`come "Gannen" ( ).
- Per ulteriori informazioni, consultate [Rappresentare le date nei calendari con più ere.](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | `false`- formato come "Gannen"<br/>`true`- formato come numero |
| **Variabile di ambiente** | N/D | N/D |
