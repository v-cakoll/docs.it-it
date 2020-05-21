---
ms.openlocfilehash: 4a34a64eba72ea24c1d830566565ce4fbee8e5b7
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721212"
---
### <a name="cellformatting-event-not-raised-if-tooltip-is-shown"></a><span data-ttu-id="39e6e-101">Evento CellFormatting non generato se viene visualizzata la descrizione comando</span><span class="sxs-lookup"><span data-stu-id="39e6e-101">CellFormatting event not raised if tooltip is shown</span></span>

<span data-ttu-id="39e6e-102">Un oggetto <xref:System.Windows.Forms.DataGridView> Mostra ora le descrizioni comandi di testo e di errore di una cella quando il mouse viene spostato e quando viene selezionato tramite la tastiera.</span><span class="sxs-lookup"><span data-stu-id="39e6e-102">A <xref:System.Windows.Forms.DataGridView> now shows a cell's text and error tooltips when hovered by a mouse and when selected via the keyboard.</span></span> <span data-ttu-id="39e6e-103">Se viene visualizzata una descrizione comando, l' <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> evento non viene generato.</span><span class="sxs-lookup"><span data-stu-id="39e6e-103">If a tooltip is shown, the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event is not raised.</span></span>

#### <a name="change-description"></a><span data-ttu-id="39e6e-104">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="39e6e-104">Change description</span></span>

<span data-ttu-id="39e6e-105">Prima di .NET Core 3,1, un oggetto <xref:System.Windows.Forms.DataGridView> con la <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> proprietà impostata su `true` mostrava una descrizione comando per il testo di una cella ed errori quando la cella veniva posizionata con il mouse.</span><span class="sxs-lookup"><span data-stu-id="39e6e-105">Prior to .NET Core 3.1, a <xref:System.Windows.Forms.DataGridView> that had the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> property set to `true` showed a tooltip for a cell's text and errors when the cell was hovered by a mouse.</span></span> <span data-ttu-id="39e6e-106">Le descrizioni comandi non sono state visualizzate quando è stata selezionata una cella tramite la tastiera, ad esempio usando il tasto TAB, i tasti di scelta rapida o la navigazione con la freccia.</span><span class="sxs-lookup"><span data-stu-id="39e6e-106">Tooltips were not shown when a cell was selected via the keyboard (for example, by using the Tab key, shortcut keys, or arrow navigation).</span></span> <span data-ttu-id="39e6e-107">Se l'utente ha modificato una cella e quindi, mentre <xref:System.Windows.Forms.DataGridView> era ancora in modalità di modifica, il puntatore del mouse su una cella che non disponeva della <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> proprietà è <xref:System.Windows.Forms.DataGridView.CellFormatting> stata impostata, è stato generato un evento per formattare il testo della cella per la visualizzazione nella cella.</span><span class="sxs-lookup"><span data-stu-id="39e6e-107">If the user edited a cell, and then, while the <xref:System.Windows.Forms.DataGridView> was still in edit mode, hovered over a cell that did not have the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> property set, a <xref:System.Windows.Forms.DataGridView.CellFormatting> event was raised to format the cell's text for display in the cell.</span></span>

<span data-ttu-id="39e6e-108">Per soddisfare gli standard di accessibilità, a partire da .NET Core 3,1, un oggetto <xref:System.Windows.Forms.DataGridView> la cui <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> proprietà è impostata su `true` Mostra descrizioni comandi per il testo di una cella ed errori non solo quando la cella viene posizionata, ma anche quando viene selezionata tramite la tastiera.</span><span class="sxs-lookup"><span data-stu-id="39e6e-108">To meet accessibility standards, starting in .NET Core 3.1, a <xref:System.Windows.Forms.DataGridView> that has the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> property set to `true` shows tooltips for a cell's text and errors not only when the cell is hovered, but also when it's selected via the keyboard.</span></span> <span data-ttu-id="39e6e-109">In seguito a questa modifica, l' <xref:System.Windows.Forms.DataGridView.CellFormatting> evento *non* viene generato quando le celle per le quali non è impostato il <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> set di proprietà vengono posizionate mentre <xref:System.Windows.Forms.DataGridView> è in modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="39e6e-109">As a consequence of this change, the <xref:System.Windows.Forms.DataGridView.CellFormatting> event is *not* raised when cells that don't have the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> property set are hovered while the <xref:System.Windows.Forms.DataGridView> is in edit mode.</span></span> <span data-ttu-id="39e6e-110">L'evento non viene generato perché il contenuto della cella al passaggio del mouse viene visualizzato come descrizione comando anziché essere visualizzato nella cella.</span><span class="sxs-lookup"><span data-stu-id="39e6e-110">The event is not raised because the content of the hovered cell is shown as a tooltip instead of being displayed in the cell.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="39e6e-111">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="39e6e-111">Version introduced</span></span>

<span data-ttu-id="39e6e-112">3.1</span><span class="sxs-lookup"><span data-stu-id="39e6e-112">3.1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="39e6e-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="39e6e-113">Recommended action</span></span>

<span data-ttu-id="39e6e-114">Effettuare il refactoring di qualsiasi codice che dipende dall' <xref:System.Windows.Forms.DataGridView.CellFormatting> evento mentre <xref:System.Windows.Forms.DataGridView> è in modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="39e6e-114">Refactor any code that depends on the <xref:System.Windows.Forms.DataGridView.CellFormatting> event while the <xref:System.Windows.Forms.DataGridView> is in edit mode.</span></span>

#### <a name="category"></a><span data-ttu-id="39e6e-115">Category</span><span class="sxs-lookup"><span data-stu-id="39e6e-115">Category</span></span>

<span data-ttu-id="39e6e-116">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="39e6e-116">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="39e6e-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="39e6e-117">Affected APIs</span></span>

<span data-ttu-id="39e6e-118">Nessuno</span><span class="sxs-lookup"><span data-stu-id="39e6e-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
