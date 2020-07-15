---
ms.openlocfilehash: 9f6703c77e17ac9376aee944b891f4635dc7632e
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309149"
---
### <a name="winforms-methods-now-throw-argumentexception"></a>I metodi WinForms ora generano ArgumentException

Alcuni Windows Forms metodi generano ora un oggetto <xref:System.ArgumentException> per gli argomenti non validi, in cui in precedenza non lo facevano.

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, il passaggio di argomenti di tipo imprevisto o non corretto a determinati metodi di Windows Forms comporterebbe uno stato indeterminato. A partire da .NET 5,0, questi metodi generano ora un oggetto <xref:System.ArgumentException> quando vengono passati argomenti non validi.

La generazione di un oggetto è <xref:System.ArgumentException> conforme al comportamento del runtime .NET. Consente inoltre di migliorare l'esperienza di debug, comunicando chiaramente quale argomento non è valido.

#### <a name="version-introduced"></a>Versione introdotta

.NET 5,0

#### <a name="recommended-action"></a>Azione consigliata

- Aggiornare il codice per impedire il passaggio di argomenti non validi.
- Se necessario, gestire un oggetto <xref:System.ArgumentException> quando si chiama il metodo.

#### <a name="category"></a>Categoria

Windows Form

#### <a name="affected-apis"></a>API interessate

Nella tabella seguente sono elencati i metodi e i parametri interessati:

| Metodo | Nome parametro | Condizione | Versione aggiunta |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | L'argomento non è di tipo <xref:System.Windows.Forms.TabPage> . | Preview 1 |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | L'argomento è `null` , <xref:System.String.Empty?displayProperty=nameWithType> o uno spazio vuoto. | Preview 5 |
| <xref:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)> | `culture` | Impossibile recuperare un oggetto `InputLanguage` per le impostazioni cultura specificate. | Anteprima 7 |

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`
- `M:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)`

-->
