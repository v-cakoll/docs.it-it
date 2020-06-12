---
ms.openlocfilehash: aab7d8538c875e35c832acc2a6c64beb84d4fb47
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702441"
---
### <a name="winforms-methods-now-throw-argumentexception"></a>I metodi WinForms ora generano ArgumentException

Alcuni Windows Forms metodi generano ora un oggetto <xref:System.ArgumentException> per gli argomenti non validi, in cui in precedenza non lo facevano.

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, il passaggio di argomenti di tipo imprevisto o non corretto a determinati metodi di Windows Forms comporterebbe uno stato indeterminato. A partire da .NET 5,0, questi metodi generano ora un oggetto <xref:System.ArgumentException> quando vengono passati argomenti non validi.

La generazione di un oggetto è <xref:System.ArgumentException> conforme al comportamento del runtime .NET. Consente inoltre di migliorare l'esperienza di debug, comunicando chiaramente quale argomento non è valido.

Nella tabella seguente sono elencati i metodi e i parametri interessati:

| Metodo | Nome parametro | Condizione | Versione aggiunta |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | L'argomento non è di tipo <xref:System.Windows.Forms.TabPage> . | 5,0 Anteprima 1 |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | L'argomento è `null` , <xref:System.String.Empty?displayProperty=nameWithType> o uno spazio vuoto. | 5,0 Preview 5 |

#### <a name="version-introduced"></a>Versione introdotta

.NET 5,0

#### <a name="recommended-action"></a>Azione consigliata

- Aggiornare il codice per impedire il passaggio di argomenti non validi.
- Se necessario, gestire un oggetto <xref:System.ArgumentException> quando si chiama il metodo.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>
- <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`

-->
