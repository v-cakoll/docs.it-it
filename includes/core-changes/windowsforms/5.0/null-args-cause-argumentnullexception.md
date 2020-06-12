---
ms.openlocfilehash: be496cd586f149ca9fd851d6aa00186e8080c66f
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84680293"
---
### <a name="winforms-methods-now-throw-argumentnullexception"></a>I metodi WinForms ora generano ArgumentNullException

Alcuni Windows Forms metodi generano ora un oggetto <xref:System.ArgumentNullException> per gli argomenti null, in cui in precedenza è stato generato un oggetto <xref:System.NullReferenceException> .

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, determinati metodi di Windows Forms generavano un' <xref:System.NullReferenceException> eccezione se veniva passato un argomento null. A partire da .NET 5,0, questi metodi generano <xref:System.ArgumentNullException> invece un oggetto per gli argomenti null.

La generazione di un oggetto è <xref:System.ArgumentNullException> conforme al comportamento del runtime .NET. Consente inoltre di migliorare l'esperienza di debug, comunicando chiaramente che un argomento è null e quale argomento è.

#### <a name="version-introduced"></a>Versione introdotta

.NET 5,0

#### <a name="recommended-action"></a>Azione consigliata

Se si chiama uno di questi metodi e il codice attualmente rileva un oggetto <xref:System.NullReferenceException> per gli argomenti null, rilevare <xref:System.ArgumentNullException> invece un oggetto. Inoltre, è consigliabile aggiornare il codice per impedire il passaggio di argomenti null ai metodi elencati.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

Nella tabella seguente sono elencati i metodi e i parametri interessati:

> [!div class="mx-tdBreakAll"]
> | Metodo | Nome parametro | Versione aggiunta |
> |-|-|-|
> | <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)> | `owner` | 5,0 Anteprima 1 |
> | <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType> | `item` | 5,0 Anteprima 1 |
> | <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)> | `container` | 5,0 Anteprima 1 |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType> | `e` | 5,0 Anteprima 1 |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | 5,0 Anteprima 1 |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | 5,0 Anteprima 1 |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType> | `e` | 5,0 Anteprima 1 |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType> > | `e` | 5,0 Anteprima 1 |
> | <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType> | `dataGridViewCellStyle` | 5,0 Anteprima 2 |
> | <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> | `data` | 5,0 Anteprima 2 |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | 5,0 Preview 5 |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | 5,0 Preview 5 |
> | <xref:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | 5,0 Preview 5 |
> | <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)> | `className` | 5,0 Preview 5 |

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.Control.ControlCollection.#ctor(System.Windows.Forms.Control)`
- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.TableLayoutControlCollection.#ctor(System.Windows.Forms.TableLayoutPanel)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)`
- `M:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)`
- `M:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)`
- `M:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)`
- `M:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)`

-->
