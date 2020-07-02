---
ms.openlocfilehash: 710d1517397f423fa40cc0c4a26c3499aac6179e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620422"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a><span data-ttu-id="1f861-101">La chiamata di Items.Refresh su un controllo WPF ListBox, ListView o DataGrid con elementi selezionati può determinare la visualizzazione di elementi duplicati nell'elemento</span><span class="sxs-lookup"><span data-stu-id="1f861-101">Calling Items.Refresh on a WPF ListBox, ListView, or DataGrid with items selected can cause duplicate items to appear in the element</span></span>

#### <a name="details"></a><span data-ttu-id="1f861-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1f861-102">Details</span></span>

<span data-ttu-id="1f861-103">In .NET Framework 4.5, la chiamata di ListBox.Items.Refresh dal codice mentre sono presenti elementi selezionati in un controllo <xref:System.Windows.Controls.ListBox?displayProperty=fullName> può causare la duplicazione degli elementi selezionati nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1f861-103">In the .NET Framework 4.5, calling ListBox.Items.Refresh from code while items are selected in a <xref:System.Windows.Controls.ListBox?displayProperty=fullName> can cause the selected items to be duplicated in the list.</span></span> <span data-ttu-id="1f861-104">Si verifica un problema analogo con <xref:System.Windows.Controls.ListView?displayProperty=fullName> e <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="1f861-104">A similar issue occurs with <xref:System.Windows.Controls.ListView?displayProperty=fullName> and <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>.</span></span> <span data-ttu-id="1f861-105">Questo problema è risolto in .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="1f861-105">This is fixed in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1f861-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="1f861-106">Suggestion</span></span>

<span data-ttu-id="1f861-107">Questo problema può essere evitato deselezionando gli elementi a livello di codice prima della chiamata di <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName>, per poi selezionarli di nuovo dopo il completamento della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1f861-107">This issue may be worked around by programmatically unselecting items before <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName> is called and then re-selecting them after the call is completed.</span></span> <span data-ttu-id="1f861-108">In alternativa, questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1f861-108">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="1f861-109">Nome</span><span class="sxs-lookup"><span data-stu-id="1f861-109">Name</span></span>    | <span data-ttu-id="1f861-110">Valore</span><span class="sxs-lookup"><span data-stu-id="1f861-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1f861-111">Scope</span><span class="sxs-lookup"><span data-stu-id="1f861-111">Scope</span></span>   |<span data-ttu-id="1f861-112">Minorenne</span><span class="sxs-lookup"><span data-stu-id="1f861-112">Minor</span></span>|
|<span data-ttu-id="1f861-113">Version</span><span class="sxs-lookup"><span data-stu-id="1f861-113">Version</span></span>|<span data-ttu-id="1f861-114">4.5</span><span class="sxs-lookup"><span data-stu-id="1f861-114">4.5</span></span>|
|<span data-ttu-id="1f861-115">Type</span><span class="sxs-lookup"><span data-stu-id="1f861-115">Type</span></span>|<span data-ttu-id="1f861-116">Runtime</span><span class="sxs-lookup"><span data-stu-id="1f861-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1f861-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="1f861-117">Affected APIs</span></span>

-<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|
