---
title: Impostazioni di configurazione della globalizzazione
description: Informazioni sulle impostazioni della fase di esecuzione che configurano gli aspetti di globalizzazione di un'app .NET Core, ad esempio il modo in cui analizza le date giapponesi.
ms.date: 05/18/2020
ms.topic: reference
ms.openlocfilehash: 56228e9a6cb6dbab6a22bdc00d11212e1019776b
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761967"
---
# <a name="run-time-configuration-options-for-globalization"></a>Opzioni di configurazione della fase di esecuzione per la globalizzazione

## <a name="invariant-mode"></a>Modalità invariante

- Determina se un'app .NET Core viene eseguita in modalità non variant di globalizzazione senza accedere a dati e comportamento specifici delle impostazioni cultura.
- Se si omette questa impostazione, l'app viene eseguita con accesso ai dati culturali. Equivale a impostare il valore su `false` .
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

- Determina se i controlli di intervallo per i calendari che supportano più ere sono rilassati o se le date che superano l'intervallo di date di un'era generano una <xref:System.ArgumentOutOfRangeException> .
- Se si omette questa impostazione, i controlli intervallo sono rilassati. Equivale a impostare il valore su `false` .
- Per altre informazioni, vedere [calendari, ere e intervalli di date: controlli intervallo rilassato](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | `false`-Controlli intervallo rilassato<br/>`true`-gli overflow generano un'eccezione |
| **Variabile di ambiente** | N/D | N/D |

## <a name="japanese-date-parsing"></a>Analisi della data giapponese

- Determina se una stringa che contiene "1" o "Gannen" come l'anno viene analizzata correttamente o se è supportato solo "1".
- Se si omette questa impostazione, le stringhe che contengono "1" o "Gannen" come analisi dell'anno hanno esito positivo. Equivale a impostare il valore su `false` .
- Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | `false`-"Gannen" o "1" è supportato<br/>`true`-è supportato solo "1" |
| **Variabile di ambiente** | N/D | N/D |

## <a name="japanese-year-format"></a>Formato dell'anno giapponese

- Determina se il primo anno di un'era del calendario giapponese è formattato come "Gannen" o come numero.
- Se si omette questa impostazione, il primo anno viene formattato come "Gannen". Equivale a impostare il valore su `false` .
- Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | `false`-Format come "Gannen"<br/>`true`-Formatta come numero |
| **Variabile di ambiente** | N/D | N/D |

## <a name="nls"></a>NLS

- Determina se .NET usa le API di globalizzazione NLS (National Language Support) o i componenti internazionali per le app di globalizzazione (ICU) per le app di Windows. .NET 5,0 e versioni successive usano le API di globalizzazione di ICU per impostazione predefinita in Windows 10 May 2019 Update e versioni successive.
- Se si omette questa impostazione, .NET usa le API di globalizzazione ICU per impostazione predefinita. Equivale a impostare il valore su `false` .
- Per altre informazioni, vedere [API di globalizzazione usare le librerie di ICU in Windows](../compatibility/3.1-5.0.md#globalization-apis-use-icu-libraries-on-windows).

| | Nome impostazione | Valori | Introdotte |
| - | - | - | - |
| **runtimeconfig. JSON** | `System.Globalization.UseNls` | `false`-Utilizzare le API di globalizzazione di ICU<br/>`true`-Utilizzare le API di globalizzazione NLS | .NET 5,0 |
| **Variabile di ambiente** | `DOTNET_SYSTEM_GLOBALIZATION_USENLS` | `false`-Utilizzare le API di globalizzazione di ICU<br/>`true`-Utilizzare le API di globalizzazione NLS | .NET 5,0 |
