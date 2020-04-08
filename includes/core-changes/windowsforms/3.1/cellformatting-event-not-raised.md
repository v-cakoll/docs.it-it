---
ms.openlocfilehash: b736ab743a628fdcbc53c5ee51551e5dad986885
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888125"
---
### <a name="cellformatting-event-not-raised-if-tooltip-is-shown"></a><span data-ttu-id="ad295-101">Evento CellFormatting non generato se è visualizzata la descrizione comando</span><span class="sxs-lookup"><span data-stu-id="ad295-101">CellFormatting event not raised if tooltip is shown</span></span>

<span data-ttu-id="ad295-102">Ora <xref:System.Windows.Forms.DataGridView> mostra il testo di una cella e le descrizioni comandi di errore quando si passa con il mouse e quando viene selezionato tramite la tastiera.</span><span class="sxs-lookup"><span data-stu-id="ad295-102">A <xref:System.Windows.Forms.DataGridView> now shows a cell's text and error tooltips when hovered by a mouse and when selected via the keyboard.</span></span> <span data-ttu-id="ad295-103">Se viene visualizzata <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> una descrizione comando, l'evento non viene generato.</span><span class="sxs-lookup"><span data-stu-id="ad295-103">If a tooltip is shown, the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event is not raised.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ad295-104">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="ad295-104">Change description</span></span>

<span data-ttu-id="ad295-105">Prima di .NET Core 3.1, un <xref:System.Windows.Forms.DataGridView> oggetto che aveva la <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> proprietà impostata su `true` mostrava una descrizione comando per il testo di una cella e gli errori quando la cella veniva posizionata da un mouse.</span><span class="sxs-lookup"><span data-stu-id="ad295-105">Prior to .NET Core 3.1, a <xref:System.Windows.Forms.DataGridView> that had the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> property set to `true` showed a tooltip for a cell's text and errors when the cell was hovered by a mouse.</span></span> <span data-ttu-id="ad295-106">Le descrizioni comandi non venivano visualizzate quando una cella è stata selezionata tramite la tastiera (ad esempio, utilizzando il tasto TAB, i tasti di scelta rapida o la navigazione con le frecce).</span><span class="sxs-lookup"><span data-stu-id="ad295-106">Tooltips were not shown when a cell was selected via the keyboard (for example, by using the Tab key, shortcut keys, or arrow navigation).</span></span> <span data-ttu-id="ad295-107">Se l'utente ha modificato una <xref:System.Windows.Forms.DataGridView> cella e quindi, mentre era ancora in modalità di modifica, si è posizionato su una cella per la cui <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> proprietà non era impostata, è stato generato un <xref:System.Windows.Forms.DataGridView.CellFormatting> evento per formattare il testo della cella da visualizzare nella cella.</span><span class="sxs-lookup"><span data-stu-id="ad295-107">If the user edited a cell, and then, while the <xref:System.Windows.Forms.DataGridView> was still in edit mode, hovered over a cell that did not have the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> property set, a <xref:System.Windows.Forms.DataGridView.CellFormatting> event was raised to format the cell's text for display in the cell.</span></span>

<span data-ttu-id="ad295-108">Per soddisfare gli standard di accessibilità, a <xref:System.Windows.Forms.DataGridView> partire da <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> .NET `true` Core 3.1, un oggetto che ha la proprietà impostata su Mostra le descrizioni comandi per il testo e gli errori di una cella non solo quando la cella è al passaggio del mouse, ma anche quando viene selezionata tramite la tastiera.</span><span class="sxs-lookup"><span data-stu-id="ad295-108">To meet accessibility standards, starting in .NET Core 3.1, a <xref:System.Windows.Forms.DataGridView> that has the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> property set to `true` shows tooltips for a cell's text and errors not only when the cell is hovered, but also when it's selected via the keyboard.</span></span> <span data-ttu-id="ad295-109">Come conseguenza di questa <xref:System.Windows.Forms.DataGridView.CellFormatting> modifica, l'evento *non* viene <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> generato quando le celle <xref:System.Windows.Forms.DataGridView> per i quali non è impostata la proprietà vengono visualizzate al passaggio del mouse mentre l'oggetto è in modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="ad295-109">As a consequence of this change, the <xref:System.Windows.Forms.DataGridView.CellFormatting> event is *not* raised when cells that don't have the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> property set are hovered while the <xref:System.Windows.Forms.DataGridView> is in edit mode.</span></span> <span data-ttu-id="ad295-110">L'evento non viene generato perché il contenuto della cella al passaggio del mouse viene visualizzato come descrizione comando anziché essere visualizzato nella cella.</span><span class="sxs-lookup"><span data-stu-id="ad295-110">The event is not raised because the content of the hovered cell is shown as a tooltip instead of being displayed in the cell.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ad295-111">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="ad295-111">Version introduced</span></span>

<span data-ttu-id="ad295-112">3.1</span><span class="sxs-lookup"><span data-stu-id="ad295-112">3.1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ad295-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="ad295-113">Recommended action</span></span>

<span data-ttu-id="ad295-114">Eseguire il refactoring <xref:System.Windows.Forms.DataGridView.CellFormatting> di qualsiasi <xref:System.Windows.Forms.DataGridView> codice che dipende dall'evento mentre l'oggetto è in modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="ad295-114">Refactor any code that depends on the <xref:System.Windows.Forms.DataGridView.CellFormatting> event while the <xref:System.Windows.Forms.DataGridView> is in edit mode.</span></span>

#### <a name="category"></a><span data-ttu-id="ad295-115">Category</span><span class="sxs-lookup"><span data-stu-id="ad295-115">Category</span></span>

<span data-ttu-id="ad295-116">Windows Form</span><span class="sxs-lookup"><span data-stu-id="ad295-116">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ad295-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="ad295-117">Affected APIs</span></span>

<span data-ttu-id="ad295-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="ad295-118">None</span></span>

<!-- 

### Affected APIs

Not detectable via API analysis.

-->
