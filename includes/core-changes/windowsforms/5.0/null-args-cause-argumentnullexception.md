---
ms.openlocfilehash: be496cd586f149ca9fd851d6aa00186e8080c66f
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84680293"
---
### <a name="winforms-methods-now-throw-argumentnullexception"></a><span data-ttu-id="54df5-101">I metodi WinForms ora generano ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="54df5-101">WinForms methods now throw ArgumentNullException</span></span>

<span data-ttu-id="54df5-102">Alcuni Windows Forms metodi generano ora un oggetto <xref:System.ArgumentNullException> per gli argomenti null, in cui in precedenza è stato generato un oggetto <xref:System.NullReferenceException> .</span><span class="sxs-lookup"><span data-stu-id="54df5-102">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="54df5-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="54df5-103">Change description</span></span>

<span data-ttu-id="54df5-104">In precedenza, determinati metodi di Windows Forms generavano un' <xref:System.NullReferenceException> eccezione se veniva passato un argomento null.</span><span class="sxs-lookup"><span data-stu-id="54df5-104">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="54df5-105">A partire da .NET 5,0, questi metodi generano <xref:System.ArgumentNullException> invece un oggetto per gli argomenti null.</span><span class="sxs-lookup"><span data-stu-id="54df5-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments, instead.</span></span>

<span data-ttu-id="54df5-106">La generazione di un oggetto è <xref:System.ArgumentNullException> conforme al comportamento del runtime .NET.</span><span class="sxs-lookup"><span data-stu-id="54df5-106">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="54df5-107">Consente inoltre di migliorare l'esperienza di debug, comunicando chiaramente che un argomento è null e quale argomento è.</span><span class="sxs-lookup"><span data-stu-id="54df5-107">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="54df5-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="54df5-108">Version introduced</span></span>

<span data-ttu-id="54df5-109">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="54df5-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="54df5-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="54df5-110">Recommended action</span></span>

<span data-ttu-id="54df5-111">Se si chiama uno di questi metodi e il codice attualmente rileva un oggetto <xref:System.NullReferenceException> per gli argomenti null, rilevare <xref:System.ArgumentNullException> invece un oggetto.</span><span class="sxs-lookup"><span data-stu-id="54df5-111">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="54df5-112">Inoltre, è consigliabile aggiornare il codice per impedire il passaggio di argomenti null ai metodi elencati.</span><span class="sxs-lookup"><span data-stu-id="54df5-112">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

#### <a name="category"></a><span data-ttu-id="54df5-113">Category</span><span class="sxs-lookup"><span data-stu-id="54df5-113">Category</span></span>

<span data-ttu-id="54df5-114">Windows Form</span><span class="sxs-lookup"><span data-stu-id="54df5-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="54df5-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="54df5-115">Affected APIs</span></span>

<span data-ttu-id="54df5-116">Nella tabella seguente sono elencati i metodi e i parametri interessati:</span><span class="sxs-lookup"><span data-stu-id="54df5-116">The following table lists the affected methods and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="54df5-117">Metodo</span><span class="sxs-lookup"><span data-stu-id="54df5-117">Method</span></span> | <span data-ttu-id="54df5-118">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="54df5-118">Parameter name</span></span> | <span data-ttu-id="54df5-119">Versione aggiunta</span><span class="sxs-lookup"><span data-stu-id="54df5-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)> | `owner` | <span data-ttu-id="54df5-120">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="54df5-120">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType> | `item` | <span data-ttu-id="54df5-121">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="54df5-121">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)> | `container` | <span data-ttu-id="54df5-122">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="54df5-122">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="54df5-123">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="54df5-123">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="54df5-124">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="54df5-124">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="54df5-125">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="54df5-125">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="54df5-126">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="54df5-126">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType> > | `e` | <span data-ttu-id="54df5-127">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="54df5-127">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType> | `dataGridViewCellStyle` | <span data-ttu-id="54df5-128">5,0 Anteprima 2</span><span class="sxs-lookup"><span data-stu-id="54df5-128">5.0 Preview 2</span></span> |
> | <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> | `data` | <span data-ttu-id="54df5-129">5,0 Anteprima 2</span><span class="sxs-lookup"><span data-stu-id="54df5-129">5.0 Preview 2</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="54df5-130">5,0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="54df5-130">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="54df5-131">5,0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="54df5-131">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | <span data-ttu-id="54df5-132">5,0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="54df5-132">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)> | `className` | <span data-ttu-id="54df5-133">5,0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="54df5-133">5.0 Preview 5</span></span> |

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
