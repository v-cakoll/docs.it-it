---
title: Impostazioni di configurazione della globalizzazione
description: Informazioni sulle impostazioni della fase di esecuzione che configurano gli aspetti di globalizzazione di un'app .NET Core, ad esempio il modo in cui analizza le date giapponesi.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 76cd4a0a0f93f4df3ff243c6024b952576e8e6cb
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740535"
---
# <a name="run-time-configuration-options-for-globalization"></a>Opzioni di configurazione della fase di esecuzione per la globalizzazione

## <a name="invariant-mode"></a>Modalità invariante

- Determina se un'app .NET Core viene eseguita in modalità invariante di globalizzazione senza accedere a dati e comportamenti specifici delle impostazioni cultura o se può accedere ai dati culturali.
- Impostazione predefinita: eseguire l'app con accesso ai dati culturali (`false`).
- Per altre informazioni, vedere [modalità invariante per la globalizzazione di .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `System.Globalization.Invariant` | `false` l'accesso ai dati culturali<br/>`true`-esecuzione in modalità invariante |
| **Variabile di ambiente** | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | `0` l'accesso ai dati culturali<br/>`1`-esecuzione in modalità invariante |

## <a name="era-year-ranges"></a>Intervalli di anni dell'era

- Determina se i controlli di intervallo per i calendari che supportano più ere sono rilassati o se le date che hanno overflow di un intervallo di date di un'era generano una <xref:System.ArgumentOutOfRangeException>.
- Impostazione predefinita: i controlli intervallo sono rilassati (`false`).
- Per altre informazioni, vedere [calendari, ere e intervalli di date: controlli intervallo rilassato](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | Controlli intervallo `false`-rilassato<br/>`true`-overflow genera un'eccezione |
| **Variabile di ambiente** | N/D | N/D |

## <a name="japanese-date-parsing"></a>Analisi della data giapponese

- Determina se una stringa che contiene "1" o "Gannen" come l'anno viene analizzata correttamente o se è supportato solo "1".
- Impostazione predefinita: analizza le stringhe che contengono "1" o "Gannen" come anno (`false`).
- Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | `false`-"Gannen" o "1" è supportato<br/>è supportato solo `true` "1" |
| **Variabile di ambiente** | N/D | N/D |

## <a name="japanese-year-format"></a>Formato dell'anno giapponese

- Determina se il primo anno di un'era del calendario giapponese è formattato come "Gannen" o come numero.
- Impostazione predefinita: formattare il primo anno come "Gannen" (`false`).
- Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | `false`-Format come "Gannen"<br/>`true`-formatta come numero |
| **Variabile di ambiente** | N/D | N/D |
