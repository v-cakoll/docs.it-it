---
ms.openlocfilehash: 00f89e6ae49982917fa7591c3283adec3947eed2
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365647"
---
### <a name="winforms-methods-now-throw-argumentnullexception"></a><span data-ttu-id="23a1a-101">I metodi WinForms ora generano ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="23a1a-101">WinForms methods now throw ArgumentNullException</span></span>

<span data-ttu-id="23a1a-102">Alcuni Windows Forms metodi generano ora un oggetto <xref:System.ArgumentNullException> per gli argomenti null, in cui in precedenza è stato generato un oggetto <xref:System.NullReferenceException> .</span><span class="sxs-lookup"><span data-stu-id="23a1a-102">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="23a1a-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="23a1a-103">Change description</span></span>

<span data-ttu-id="23a1a-104">In precedenza, determinati metodi di Windows Forms generavano un' <xref:System.NullReferenceException> eccezione se veniva passato un argomento null.</span><span class="sxs-lookup"><span data-stu-id="23a1a-104">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="23a1a-105">A partire da .NET 5,0, questi metodi generano <xref:System.ArgumentNullException> invece un oggetto per gli argomenti null.</span><span class="sxs-lookup"><span data-stu-id="23a1a-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments, instead.</span></span>

<span data-ttu-id="23a1a-106">La generazione di un oggetto è <xref:System.ArgumentNullException> conforme al comportamento del runtime .NET.</span><span class="sxs-lookup"><span data-stu-id="23a1a-106">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="23a1a-107">Consente inoltre di migliorare l'esperienza di debug, comunicando chiaramente che un argomento è null e quale argomento è.</span><span class="sxs-lookup"><span data-stu-id="23a1a-107">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="23a1a-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="23a1a-108">Version introduced</span></span>

<span data-ttu-id="23a1a-109">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="23a1a-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="23a1a-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="23a1a-110">Recommended action</span></span>

<span data-ttu-id="23a1a-111">Se si chiama uno di questi metodi e il codice attualmente rileva un oggetto <xref:System.NullReferenceException> per gli argomenti null, rilevare <xref:System.ArgumentNullException> invece un oggetto.</span><span class="sxs-lookup"><span data-stu-id="23a1a-111">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="23a1a-112">Inoltre, è consigliabile aggiornare il codice per impedire il passaggio di argomenti null ai metodi elencati.</span><span class="sxs-lookup"><span data-stu-id="23a1a-112">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

#### <a name="category"></a><span data-ttu-id="23a1a-113">Category</span><span class="sxs-lookup"><span data-stu-id="23a1a-113">Category</span></span>

<span data-ttu-id="23a1a-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="23a1a-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="23a1a-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="23a1a-115">Affected APIs</span></span>

<span data-ttu-id="23a1a-116">Nella tabella seguente sono elencati i metodi e i parametri interessati:</span><span class="sxs-lookup"><span data-stu-id="23a1a-116">The following table lists the affected methods and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="23a1a-117">Metodo</span><span class="sxs-lookup"><span data-stu-id="23a1a-117">Method</span></span> | <span data-ttu-id="23a1a-118">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="23a1a-118">Parameter name</span></span> | <span data-ttu-id="23a1a-119">Versione aggiunta</span><span class="sxs-lookup"><span data-stu-id="23a1a-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)> | `owner` | <span data-ttu-id="23a1a-120">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="23a1a-120">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType> | `item` | <span data-ttu-id="23a1a-121">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="23a1a-121">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)> | `container` | <span data-ttu-id="23a1a-122">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="23a1a-122">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="23a1a-123">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="23a1a-123">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="23a1a-124">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="23a1a-124">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="23a1a-125">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="23a1a-125">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="23a1a-126">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="23a1a-126">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType> > | `e` | <span data-ttu-id="23a1a-127">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="23a1a-127">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType> | `dataGridViewCellStyle` | <span data-ttu-id="23a1a-128">5,0 Anteprima 2</span><span class="sxs-lookup"><span data-stu-id="23a1a-128">5.0 Preview 2</span></span> |
> | <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> | `data` | <span data-ttu-id="23a1a-129">5,0 Anteprima 2</span><span class="sxs-lookup"><span data-stu-id="23a1a-129">5.0 Preview 2</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="23a1a-130">5,0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="23a1a-130">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="23a1a-131">5,0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="23a1a-131">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | <span data-ttu-id="23a1a-132">5,0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="23a1a-132">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)> | `className` | <span data-ttu-id="23a1a-133">5,0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="23a1a-133">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="23a1a-134">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="23a1a-134">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])> | <span data-ttu-id="23a1a-135">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="23a1a-135">`owner`, `value`</span></span> | <span data-ttu-id="23a1a-136">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="23a1a-136">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)> | <span data-ttu-id="23a1a-137">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="23a1a-137">`owner`, `value`</span></span> | <span data-ttu-id="23a1a-138">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="23a1a-138">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])?displayProperty=nameWithType> | `items` | <span data-ttu-id="23a1a-139">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="23a1a-139">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)?displayProperty=nameWithType> | `value` | <span data-ttu-id="23a1a-140">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="23a1a-140">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="23a1a-141">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="23a1a-141">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="23a1a-142">`destination`d</span><span class="sxs-lookup"><span data-stu-id="23a1a-142">`destination`q\`</span></span> | <span data-ttu-id="23a1a-143">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="23a1a-143">5.0 Preview 6</span></span> |

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
- `M:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)`

-->
