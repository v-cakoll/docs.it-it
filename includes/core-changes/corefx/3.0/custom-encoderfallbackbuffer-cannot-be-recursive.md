---
ms.openlocfilehash: 00c32c10f77995284264e795d386f699082dcb84
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721364"
---
### <a name="custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively"></a>Le istanze EncoderFallbackBuffer personalizzate non possono eseguire il fallback in modo ricorsivo

Le <xref:System.Text.EncoderFallbackBuffer> istanze personalizzate non possono eseguire il fallback in modo ricorsivo. L'implementazione di <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> deve produrre una sequenza di caratteri convertibile nella codifica di destinazione. In caso contrario, si verificherà un'eccezione.

#### <a name="change-description"></a>Descrizione modifica:

Durante un'operazione di transcodifica da carattere a byte, il runtime rileva le sequenze UTF-16 non conformi o non convertibili e fornisce tali caratteri al <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> metodo. Il `Fallback` metodo determina i caratteri che devono essere sostituiti dai dati non convertibili originali e questi caratteri vengono svuotati chiamando <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> in un ciclo.

Il runtime tenta quindi di transcodificare questi caratteri di sostituzione nella codifica di destinazione. Se l'operazione ha esito positivo, il runtime continua la transcodifica dal punto in cui è stato interrotto nella stringa di input originale.

In .NET Core Preview 7 e versioni precedenti, le implementazioni personalizzate di <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> possono restituire sequenze di caratteri che non sono convertibili nella codifica di destinazione. Se i caratteri sostituiti non possono essere transcodificati nella codifica di destinazione, il runtime richiama di <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> nuovo il metodo con i caratteri di sostituzione, aspettando <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> che il metodo restituisca una nuova sequenza di sostituzione. Questo processo continua fino a quando il runtime non rileva una sostituzione corretta, convertibile o fino a quando non viene raggiunto il numero massimo di ricorsioni.

A partire da .NET Core 3,0, le implementazioni personalizzate di <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> devono restituire sequenze di caratteri convertibili nella codifica di destinazione. Se i caratteri sostituiti non possono essere trascodificati nella codifica di destinazione, <xref:System.ArgumentException> viene generata un'eccezione. Il runtime non effettuerà più chiamate ricorsive nell' <xref:System.Text.EncoderFallbackBuffer> istanza.

Questo comportamento si applica solo quando vengono soddisfatte tutte e tre le condizioni seguenti:

- Il runtime rileva una sequenza UTF-16 non corretta o una sequenza UTF-16 che non può essere convertita nella codifica di destinazione.
- <xref:System.Text.EncoderFallback>È stato specificato un oggetto personalizzato.
- L'oggetto personalizzato <xref:System.Text.EncoderFallback> tenta di sostituire una nuova sequenza UTF-16 non in formato non corretto o non convertibile.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

La maggior parte degli sviluppatori non deve intraprendere alcuna azione.

Se un'applicazione usa una <xref:System.Text.EncoderFallback> classe e personalizzata <xref:System.Text.EncoderFallbackBuffer> , assicurarsi che l'implementazione di <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> compilerà il buffer di fallback con dati UTF-16 ben formati convertibili direttamente nella codifica di destinazione quando il <xref:System.Text.EncoderFallbackBuffer.Fallback%2A> metodo viene richiamato per la prima volta dal runtime.

#### <a name="category"></a>Category

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

- <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>
- <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.EncoderFallbackBuffer.Fallback`
- `M:System.Text.EncoderFallbackBuffer.GetNextChar`

-->
