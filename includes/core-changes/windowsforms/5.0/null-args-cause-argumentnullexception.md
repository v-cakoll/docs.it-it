---
ms.openlocfilehash: fc0eec26073c299887b4748d0ad37e21c7294e84
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275168"
---
### <a name="winforms-apis-now-throw-argumentnullexception"></a><span data-ttu-id="b0c39-101">API WinForms ora generano ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="b0c39-101">WinForms APIs now throw ArgumentNullException</span></span>

<span data-ttu-id="b0c39-102">Alcuni metodi di Windows <xref:System.ArgumentNullException> Form ora generano un <xref:System.NullReferenceException>for argomenti null, in cui in precedenza hanno lanciato un oggetto .</span><span class="sxs-lookup"><span data-stu-id="b0c39-102">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b0c39-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="b0c39-103">Change description</span></span>

<span data-ttu-id="b0c39-104">In precedenza, alcuni metodi <xref:System.NullReferenceException> Windows Form ha generato un if passato un argomento che era null.</span><span class="sxs-lookup"><span data-stu-id="b0c39-104">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="b0c39-105">A partire da .NET 5.0, <xref:System.ArgumentNullException> questi metodi ora generano un for null argomenti invece.</span><span class="sxs-lookup"><span data-stu-id="b0c39-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments instead.</span></span>

<span data-ttu-id="b0c39-106">La generazione <xref:System.ArgumentNullException> di un'eccezione è conforme al comportamento del runtime di .NET.</span><span class="sxs-lookup"><span data-stu-id="b0c39-106">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="b0c39-107">Migliora inoltre l'esperienza di debug comunicando chiaramente che un argomento è null e quale argomento è.</span><span class="sxs-lookup"><span data-stu-id="b0c39-107">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b0c39-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="b0c39-108">Version introduced</span></span>

<span data-ttu-id="b0c39-109">Anteprima di .NET 5.0 1</span><span class="sxs-lookup"><span data-stu-id="b0c39-109">.NET 5.0 Preview 1\</span></span>
<span data-ttu-id="b0c39-110">.NET 5.0 Anteprima 2</span><span class="sxs-lookup"><span data-stu-id="b0c39-110">.NET 5.0 Preview 2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b0c39-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="b0c39-111">Recommended action</span></span>

<span data-ttu-id="b0c39-112">Se si chiama uno di questi metodi e <xref:System.NullReferenceException> il codice attualmente <xref:System.ArgumentNullException> rileva un per null argomenti, catch an invece.</span><span class="sxs-lookup"><span data-stu-id="b0c39-112">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="b0c39-113">Inoltre, è consigliabile aggiornare il codice per impedire il passaggio di argomenti null ai metodi elencati.</span><span class="sxs-lookup"><span data-stu-id="b0c39-113">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

#### <a name="category"></a><span data-ttu-id="b0c39-114">Category</span><span class="sxs-lookup"><span data-stu-id="b0c39-114">Category</span></span>

<span data-ttu-id="b0c39-115">Windows Form</span><span class="sxs-lookup"><span data-stu-id="b0c39-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b0c39-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="b0c39-116">Affected APIs</span></span>

<span data-ttu-id="b0c39-117">A partire da .NET 5.0 Preview 1:</span><span class="sxs-lookup"><span data-stu-id="b0c39-117">Starting in .NET 5.0 Preview 1:</span></span>

- <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)>
- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType>

<span data-ttu-id="b0c39-118">A partire da .NET 5.0 Preview 2:</span><span class="sxs-lookup"><span data-stu-id="b0c39-118">Starting in .NET 5.0 Preview 2:</span></span>

- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType>
- <span data-ttu-id="b0c39-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType>(solo <xref:System.IO.Stream> per il parametro)</span><span class="sxs-lookup"><span data-stu-id="b0c39-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> (for the <xref:System.IO.Stream> parameter only)</span></span>

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
