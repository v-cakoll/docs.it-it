---
ms.openlocfilehash: ab8d801f3cdcfbeb6de20146754b26e3713d7dd6
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702491"
---
### <a name="winforms-methods-now-throw-argumentnullexception"></a><span data-ttu-id="1c220-101">I metodi WinForms ora generano ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="1c220-101">WinForms methods now throw ArgumentNullException</span></span>

<span data-ttu-id="1c220-102">Alcuni Windows Forms metodi generano ora un oggetto <xref:System.ArgumentNullException> per gli argomenti null, in cui in precedenza è stato generato un oggetto <xref:System.NullReferenceException> .</span><span class="sxs-lookup"><span data-stu-id="1c220-102">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1c220-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="1c220-103">Change description</span></span>

<span data-ttu-id="1c220-104">In precedenza, determinati metodi di Windows Forms generavano un' <xref:System.NullReferenceException> eccezione se veniva passato un argomento null.</span><span class="sxs-lookup"><span data-stu-id="1c220-104">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="1c220-105">A partire da .NET 5,0, questi metodi generano ora un oggetto <xref:System.ArgumentNullException> per gli argomenti null.</span><span class="sxs-lookup"><span data-stu-id="1c220-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments instead.</span></span>

<span data-ttu-id="1c220-106">La generazione di un oggetto è <xref:System.ArgumentNullException> conforme al comportamento del runtime .NET.</span><span class="sxs-lookup"><span data-stu-id="1c220-106">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="1c220-107">Consente inoltre di migliorare l'esperienza di debug, comunicando chiaramente che un argomento è null e quale argomento è.</span><span class="sxs-lookup"><span data-stu-id="1c220-107">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1c220-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="1c220-108">Version introduced</span></span>

<span data-ttu-id="1c220-109">.NET 5,0 Preview 1 </span><span class="sxs-lookup"><span data-stu-id="1c220-109">.NET 5.0 Preview 1</span></span>\
<span data-ttu-id="1c220-110">.NET 5,0 Preview 2</span><span class="sxs-lookup"><span data-stu-id="1c220-110">.NET 5.0 Preview 2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1c220-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="1c220-111">Recommended action</span></span>

<span data-ttu-id="1c220-112">Se si chiama uno di questi metodi e il codice attualmente rileva un oggetto <xref:System.NullReferenceException> per gli argomenti null, rilevare <xref:System.ArgumentNullException> invece un oggetto.</span><span class="sxs-lookup"><span data-stu-id="1c220-112">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="1c220-113">Inoltre, è consigliabile aggiornare il codice per impedire il passaggio di argomenti null ai metodi elencati.</span><span class="sxs-lookup"><span data-stu-id="1c220-113">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

#### <a name="category"></a><span data-ttu-id="1c220-114">Category</span><span class="sxs-lookup"><span data-stu-id="1c220-114">Category</span></span>

<span data-ttu-id="1c220-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c220-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1c220-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="1c220-116">Affected APIs</span></span>

<span data-ttu-id="1c220-117">A partire da .NET 5,0 Preview 1:</span><span class="sxs-lookup"><span data-stu-id="1c220-117">Starting in .NET 5.0 Preview 1:</span></span>

- <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)>
- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType>

<span data-ttu-id="1c220-118">A partire da .NET 5,0 Preview 2:</span><span class="sxs-lookup"><span data-stu-id="1c220-118">Starting in .NET 5.0 Preview 2:</span></span>

- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType>
- <span data-ttu-id="1c220-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType>(solo per il <xref:System.IO.Stream> parametro)</span><span class="sxs-lookup"><span data-stu-id="1c220-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> (for the <xref:System.IO.Stream> parameter only)</span></span>

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

-->
