---
ms.openlocfilehash: 58d1c8cd3aff52703522391c14348bd81c108587
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237382"
---
### <a name="custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively"></a>Le istanze EncoderFallbackBuffer personalizzate non possono eseguire il fallback in modo ricorsivo

Le istanze personalizzate <xref:System.Text.EncoderFallbackBuffer> non possono eseguire il fallback in modo ricorsivo. L'implementazione di <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> deve produrre una sequenza di caratteri convertibile nella codifica di destinazione. In caso contrario, si verificherà un'eccezione.

#### <a name="change-description"></a>Descrizione della modifica

Durante un'operazione di transcodifica da carattere a byte, il runtime rileva sequenze UTF-16 non conformi o non convertibili e fornisce tali caratteri al metodo <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>. Il metodo `Fallback` determina i caratteri che devono essere sostituiti dai dati non convertibili originali e questi caratteri vengono svuotati chiamando <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> in un ciclo.

Il runtime tenta quindi di transcodificare questi caratteri di sostituzione nella codifica di destinazione. Se l'operazione ha esito positivo, il runtime continua la transcodifica dal punto in cui è stato interrotto nella stringa di input originale.

In .NET Core Preview 7 e versioni precedenti, le implementazioni personalizzate di <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> possono restituire sequenze di caratteri che non possono essere convertite nella codifica di destinazione. Se i caratteri sostituiti non possono essere transcodificati nella codifica di destinazione, il runtime richiama di nuovo il metodo <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> con i caratteri di sostituzione, aspettando che il metodo <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> restituisca una nuova sequenza di sostituzione. Questo processo continua fino a quando il runtime non rileva una sostituzione corretta, convertibile o fino a quando non viene raggiunto il numero massimo di ricorsioni.

A partire da .NET Core 3,0, le implementazioni personalizzate di <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> devono restituire sequenze di caratteri convertibili nella codifica di destinazione. Se i caratteri sostituiti non possono essere transcodificati nella codifica di destinazione, viene generata un'<xref:System.ArgumentException>. Il runtime non effettuerà più chiamate ricorsive nell'istanza <xref:System.Text.EncoderFallbackBuffer>.

Questo comportamento si applica solo quando vengono soddisfatte tutte e tre le condizioni seguenti:

- Il runtime rileva una sequenza UTF-16 non corretta o una sequenza UTF-16 che non può essere convertita nella codifica di destinazione.
- È stato specificato un <xref:System.Text.EncoderFallback> personalizzato.
- Il <xref:System.Text.EncoderFallback> personalizzato tenta di sostituire una nuova sequenza UTF-16 non formattata o non convertibile.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

La maggior parte degli sviluppatori non deve intraprendere alcuna azione.

Se un'applicazione usa una classe <xref:System.Text.EncoderFallback> e <xref:System.Text.EncoderFallbackBuffer> personalizzata, assicurarsi che l'implementazione di <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> compileri il buffer di fallback con dati UTF-16 ben formati convertibili direttamente nella codifica di destinazione quando il metodo <xref:System.Text.EncoderFallbackBuffer.Fallback%2A> viene prima richiamato dal Runtime.

#### <a name="category"></a>Category

CoreFx

#### <a name="affected-apis"></a>API interessate

- <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>
- <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.EncoderFallbackBuffer.Fallback`
- `M:System.Text.EncoderFallbackBuffer.GetNextChar`

-->
