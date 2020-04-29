---
title: Impostazioni di configurazione della globalizzazione
description: Informazioni sulle impostazioni della fase di esecuzione che configurano gli aspetti di globalizzazione di un'app .NET Core, ad esempio il modo in cui analizza le date giapponesi.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 7668c345181d7c08cfca9c5cb76b8addd76223ec
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506805"
---
# <a name="run-time-configuration-options-for-globalization"></a>Opzioni di configurazione della fase di esecuzione per la globalizzazione

## <a name="invariant-mode"></a>Modalità invariante

- Determina se un'app .NET Core viene eseguita in modalità non variant di globalizzazione senza accedere a dati e comportamento specifici delle impostazioni cultura.
- Impostazione predefinita: eseguire l'app con accesso ai dati culturali`false`().
- Per altre informazioni, vedere [modalità invariante per la globalizzazione di .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `System.Globalization.Invariant` | `false`-accesso ai dati culturali<br/>`true`-esecuzione in modalità invariante |
| **MSBuild (proprietà)** | `InvariantGlobalization` | `false`-accesso ai dati culturali<br/>`true`-esecuzione in modalità invariante |
| **Variabile di ambiente** | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | `0`-accesso ai dati culturali<br/>`1`-esecuzione in modalità invariante |

### <a name="examples"></a>Esempi

file *runtimeconfig. JSON* :

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

## <a name="era-year-ranges"></a>Intervalli di anni dell'era

- Determina se i controlli di intervallo per i calendari che supportano più ere sono rilassati o se le date che superano l' <xref:System.ArgumentOutOfRangeException>intervallo di date di un'era generano una.
- Impostazione predefinita: i controlli intervallo sono`false`rilassati ().
- Per altre informazioni, vedere [calendari, ere e intervalli di date: controlli intervallo rilassato](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | `false`-Controlli intervallo rilassato<br/>`true`-gli overflow generano un'eccezione |
| **Variabile di ambiente** | N/D | N/D |

## <a name="japanese-date-parsing"></a>Analisi della data giapponese

- Determina se una stringa che contiene "1" o "Gannen" come l'anno viene analizzata correttamente o se è supportato solo "1".
- Impostazione predefinita: analizza le stringhe che contengono "1" o "Gannen" come anno (`false`).
- Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | `false`-"Gannen" o "1" è supportato<br/>`true`-è supportato solo "1" |
| **Variabile di ambiente** | N/D | N/D |

## <a name="japanese-year-format"></a>Formato dell'anno giapponese

- Determina se il primo anno di un'era del calendario giapponese è formattato come "Gannen" o come numero.
- Impostazione predefinita: formattare il primo anno come "Gannen"`false`().
- Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | `false`-Format come "Gannen"<br/>`true`-Formatta come numero |
| **Variabile di ambiente** | N/D | N/D |
