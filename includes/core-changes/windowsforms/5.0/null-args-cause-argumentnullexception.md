---
ms.openlocfilehash: 7a6b0b15de4295506ff03b8566c06010b918566c
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158397"
---
### <a name="winforms-methods-now-throw-argumentnullexception"></a><span data-ttu-id="f2365-101">I metodi WinForms ora generano ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="f2365-101">WinForms methods now throw ArgumentNullException</span></span>

<span data-ttu-id="f2365-102">Alcuni Windows Forms metodi generano ora <xref:System.ArgumentNullException> un oggetto per gli argomenti null, in cui <xref:System.NullReferenceException>in precedenza è stato generato un oggetto.</span><span class="sxs-lookup"><span data-stu-id="f2365-102">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f2365-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="f2365-103">Change description</span></span>

<span data-ttu-id="f2365-104">In precedenza, determinati metodi di Windows Forms <xref:System.NullReferenceException> generavano un'eccezione se veniva passato un argomento null.</span><span class="sxs-lookup"><span data-stu-id="f2365-104">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="f2365-105">A partire da .NET 5,0, questi metodi generano <xref:System.ArgumentNullException> ora un oggetto per gli argomenti null.</span><span class="sxs-lookup"><span data-stu-id="f2365-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments instead.</span></span>

<span data-ttu-id="f2365-106">La generazione <xref:System.ArgumentNullException> di un oggetto è conforme al comportamento del runtime .NET.</span><span class="sxs-lookup"><span data-stu-id="f2365-106">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="f2365-107">Consente inoltre di migliorare l'esperienza di debug, comunicando chiaramente che un argomento è null e quale argomento è.</span><span class="sxs-lookup"><span data-stu-id="f2365-107">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f2365-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="f2365-108">Version introduced</span></span>

<span data-ttu-id="f2365-109">.NET 5,0 Preview 1 </span><span class="sxs-lookup"><span data-stu-id="f2365-109">.NET 5.0 Preview 1</span></span>\
<span data-ttu-id="f2365-110">.NET 5,0 Preview 2</span><span class="sxs-lookup"><span data-stu-id="f2365-110">.NET 5.0 Preview 2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f2365-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="f2365-111">Recommended action</span></span>

<span data-ttu-id="f2365-112">Se si chiama uno di questi metodi e il codice attualmente rileva un oggetto <xref:System.NullReferenceException> per gli argomenti null, rilevare <xref:System.ArgumentNullException> invece un oggetto.</span><span class="sxs-lookup"><span data-stu-id="f2365-112">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="f2365-113">Inoltre, è consigliabile aggiornare il codice per impedire il passaggio di argomenti null ai metodi elencati.</span><span class="sxs-lookup"><span data-stu-id="f2365-113">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

#### <a name="category"></a><span data-ttu-id="f2365-114">Category</span><span class="sxs-lookup"><span data-stu-id="f2365-114">Category</span></span>

<span data-ttu-id="f2365-115">Windows Form</span><span class="sxs-lookup"><span data-stu-id="f2365-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f2365-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="f2365-116">Affected APIs</span></span>

<span data-ttu-id="f2365-117">A partire da .NET 5,0 Preview 1:</span><span class="sxs-lookup"><span data-stu-id="f2365-117">Starting in .NET 5.0 Preview 1:</span></span>

- <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)>
- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType>

<span data-ttu-id="f2365-118">A partire da .NET 5,0 Preview 2:</span><span class="sxs-lookup"><span data-stu-id="f2365-118">Starting in .NET 5.0 Preview 2:</span></span>

- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType>
- <span data-ttu-id="f2365-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType>(solo per <xref:System.IO.Stream> il parametro)</span><span class="sxs-lookup"><span data-stu-id="f2365-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> (for the <xref:System.IO.Stream> parameter only)</span></span>

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
