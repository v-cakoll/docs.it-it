---
ms.openlocfilehash: 5212c5d9513a8ef5f51693857d0ddb60db4e49b9
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158398"
---
### <a name="winforms-methods-now-throw-argumentexception"></a>I metodi WinForms ora generano ArgumentException

Alcuni Windows Forms metodi generano ora <xref:System.ArgumentException> un oggetto per gli argomenti non validi, in cui in precedenza non lo facevano.

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, il passaggio di argomenti di tipo imprevisto o non corretto a determinati metodi di Windows Forms comporterebbe uno stato indeterminato. A partire da .NET 5,0, questi metodi generano <xref:System.ArgumentException> ora un oggetto quando vengono passati argomenti non validi.

La generazione <xref:System.ArgumentException> di un oggetto è conforme al comportamento del runtime .NET. Consente inoltre di migliorare l'esperienza di debug, comunicando chiaramente quale argomento non è valido.

Nella tabella seguente sono elencati i metodi e i parametri interessati:

| Metodo | Nome parametro | Condizione | Versione aggiunta |
|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | L'argomento non è di <xref:System.Windows.Forms.TabPage>tipo. | 5,0 Anteprima 1 |

#### <a name="version-introduced"></a>Versione introdotta

.NET 5,0 Preview 1

#### <a name="recommended-action"></a>Azione consigliata

- Aggiornare il codice per impedire il passaggio di argomenti non validi.
- Se necessario, gestire un <xref:System.ArgumentException> oggetto quando si chiama il metodo.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`

-->
