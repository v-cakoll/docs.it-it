---
ms.openlocfilehash: fc0eec26073c299887b4748d0ad37e21c7294e84
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275168"
---
### <a name="winforms-apis-now-throw-argumentnullexception"></a>API WinForms ora generano ArgumentNullException

Alcuni metodi di Windows <xref:System.ArgumentNullException> Form ora generano un <xref:System.NullReferenceException>for argomenti null, in cui in precedenza hanno lanciato un oggetto .

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, alcuni metodi <xref:System.NullReferenceException> Windows Form ha generato un if passato un argomento che era null. A partire da .NET 5.0, <xref:System.ArgumentNullException> questi metodi ora generano un for null argomenti invece.

La generazione <xref:System.ArgumentNullException> di un'eccezione è conforme al comportamento del runtime di .NET. Migliora inoltre l'esperienza di debug comunicando chiaramente che un argomento è null e quale argomento è.

#### <a name="version-introduced"></a>Versione introdotta

Anteprima di .NET 5.0 1
.NET 5.0 Anteprima 2

#### <a name="recommended-action"></a>Azione consigliata

Se si chiama uno di questi metodi e <xref:System.NullReferenceException> il codice attualmente <xref:System.ArgumentNullException> rileva un per null argomenti, catch an invece. Inoltre, è consigliabile aggiornare il codice per impedire il passaggio di argomenti null ai metodi elencati.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

A partire da .NET 5.0 Preview 1:

- <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)>
- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType>

A partire da .NET 5.0 Preview 2:

- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType>(solo <xref:System.IO.Stream> per il parametro)

<!-- 

### Affected APIs

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

-->
