---
ms.openlocfilehash: f1fc70075ef09a4f036c69788342c07ee51d72ce
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702446"
---
### <a name="winforms-methods-now-throw-argumentexception"></a>I metodi WinForms ora generano ArgumentException

Alcuni Windows Forms metodi generano ora un oggetto <xref:System.ArgumentException> per gli argomenti non validi, in cui in precedenza non lo facevano.

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, il passaggio di argomenti di tipo imprevisto o non corretto a determinati metodi di Windows Forms comporterebbe uno stato indeterminato. A partire da .NET 5,0, questi metodi generano ora un oggetto <xref:System.ArgumentException> quando vengono passati argomenti non validi.

La generazione di un oggetto è <xref:System.ArgumentException> conforme al comportamento del runtime .NET. Consente inoltre di migliorare l'esperienza di debug, comunicando chiaramente quale argomento non è valido.

Nella tabella seguente sono elencati i metodi e i parametri interessati:

| Metodo | Nome parametro | Condizione | Versione aggiunta |
|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | L'argomento non è di tipo <xref:System.Windows.Forms.TabPage> . | 5,0 Anteprima 1 |

#### <a name="version-introduced"></a>Versione introdotta

.NET 5,0 Preview 1

#### <a name="recommended-action"></a>Azione consigliata

- Aggiornare il codice per impedire il passaggio di argomenti non validi.
- Se necessario, gestire un oggetto <xref:System.ArgumentException> quando si chiama il metodo.

#### <a name="category"></a>Category

Windows Forms

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`

-->
