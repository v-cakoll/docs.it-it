---
ms.openlocfilehash: f42da00487735acdcc60f876c75e1dfd17103008
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702442"
---
### <a name="winforms-properties-now-throw-argumentoutofrangeexception"></a>Le proprietà di WinForms ora generano ArgumentOutOfRangeException

Alcune proprietà di Windows Forms generano ora un oggetto <xref:System.ArgumentOutOfRangeException> per gli argomenti non validi, in cui in precedenza non lo facevano.

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, queste proprietà generavano varie eccezioni, ad esempio <xref:System.NullReferenceException> , <xref:System.IndexOutOfRangeException> o <xref:System.ArgumentException> , quando venivano passati argomenti fuori intervallo. A partire da .NET 5,0, queste proprietà generano ora un oggetto <xref:System.ArgumentOutOfRangeException> quando vengono passati argomenti che non rientrano nell'intervallo.

La generazione di un oggetto è <xref:System.ArgumentOutOfRangeException> conforme al comportamento del runtime .NET. Consente inoltre di migliorare l'esperienza di debug, comunicando chiaramente quale argomento non è valido.

#### <a name="version-introduced"></a>Versione introdotta

.NET 5,0

#### <a name="recommended-action"></a>Azione consigliata

- Aggiornare il codice per impedire il passaggio di argomenti non validi.
- Se necessario, gestire un oggetto <xref:System.ArgumentOutOfRangeException> quando si imposta la proprietà.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

La tabella seguente elenca le proprietà e i parametri interessati:

> [!div class="mx-tdBreakAll"]
> | Proprietà | Nome parametro | Versione aggiunta |
> |-|-|-|
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)?displayProperty=nameWithType> | `index` | 5,0 Preview 5 |
> | <xref:System.Windows.Forms.TreeNode.ImageIndex?displayProperty=nameWithType> | `value` | 5,0 Preview 6 |
> | <xref:System.Windows.Forms.TreeNode.SelectedImageIndex?displayProperty=nameWithType> | `value` | 5,0 Preview 6 |

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)`
- `P:System.Windows.Forms.TreeNode.ImageIndex`
- `P:System.Windows.Forms.TreeNode.SelectedImageIndex`

-->
