---
ms.openlocfilehash: 820825f0545aa78729414c388385b339225b1235
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021620"
---
### <a name="custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively"></a>Le istanze di EncoderFallbackBuffer personalizzate non possono eseguire il fallback in modo ricorsivoCustom EncoderFallbackBuffer instances cannot fallback recursively

Le <xref:System.Text.EncoderFallbackBuffer> istanze personalizzate non possono eseguire il rollback in modo ricorsivo. L'implementazione di <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> deve generare una sequenza di caratteri convertibile nella codifica di destinazione. In caso contrario, si verifica un'eccezione.

#### <a name="change-description"></a>Descrizione modifica:

Durante un'operazione di transcodifica da carattere a byte, il runtime rileva sequenze UTF-16 in <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> formato non corretto o non convertibili e fornisce tali caratteri al metodo. Il `Fallback` metodo determina quali caratteri devono essere sostituiti con i dati non convertibili originali e questi caratteri vengono scaricati chiamando <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> in un ciclo.

Il runtime tenta quindi di transcodificare questi caratteri di sostituzione nella codifica di destinazione. Se l'operazione ha esito positivo, il runtime continua la transcodifica dal punto in cui è stata interrotta nella stringa di input originale.

In .NET Core Preview 7 e versioni <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> precedenti, le implementazioni personalizzate di possono restituire sequenze di caratteri non convertibili nella codifica di destinazione. Se i caratteri sostituiti non possono essere transcodificati nella <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> codifica di destinazione, il <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> runtime richiama nuovamente il metodo con i caratteri di sostituzione, prevedendo che il metodo restituisca una nuova sequenza di sostituzione. Questo processo continua fino a quando il runtime vede una sostituzione convertibile ben formata o fino a quando non viene raggiunto un conteggio di ricorsione massimo.

A partire da .NET Core 3.0, le implementazioni personalizzate di devono restituire sequenze di <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> caratteri convertibili nella codifica di destinazione. Se i caratteri sostituiti non possono essere transcodificati nella codifica di destinazione, viene generata un'eccezione. <xref:System.ArgumentException> Il runtime non effettuerà più chiamate <xref:System.Text.EncoderFallbackBuffer> ricorsive nell'istanza.

Questo comportamento si applica solo quando vengono soddisfatte tutte e tre le condizioni seguenti:This behavior only applies when all three of the following conditions are met:

- Il runtime rileva una sequenza UTF-16 in formato non corretto o una sequenza UTF-16 che non può essere convertita nella codifica di destinazione.
- È <xref:System.Text.EncoderFallback> stata specificata una proprietà personalizzata.
- L'elemento personalizzato <xref:System.Text.EncoderFallback> tenta di sostituire una nuova sequenza UTF-16 non formata correttamente o non convertibile.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

La maggior parte degli sviluppatori non deve intraprendere alcuna azione.

Se un'applicazione <xref:System.Text.EncoderFallback> utilizza <xref:System.Text.EncoderFallbackBuffer> una classe e <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> personalizzata, verificare che l'implementazione di popola il buffer di <xref:System.Text.EncoderFallbackBuffer.Fallback%2A> fallback con dati UTF-16 ben formati che sono direttamente convertibili nella codifica di destinazione quando il metodo viene richiamato per la prima volta dal runtime.

#### <a name="category"></a>Category

Librerie .NET di base

#### <a name="affected-apis"></a>API interessate

- <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>
- <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.EncoderFallbackBuffer.Fallback`
- `M:System.Text.EncoderFallbackBuffer.GetNextChar`

-->
