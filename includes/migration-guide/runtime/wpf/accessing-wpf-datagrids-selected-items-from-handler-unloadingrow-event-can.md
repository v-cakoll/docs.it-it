---
ms.openlocfilehash: 7ac0cac53ab2fa7657d0ae58f11d9e777631acc9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620437"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a><span data-ttu-id="ce69a-101">L'accesso agli elementi selezionati di un elemento DataGrid WPF da parte di un gestore dell'evento UnloadingRow di DataGrid può determinare un'eccezione NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="ce69a-101">Accessing a WPF DataGrid's selected items from a handler of the DataGrid's UnloadingRow event can cause a NullReferenceException</span></span>

#### <a name="details"></a><span data-ttu-id="ce69a-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ce69a-102">Details</span></span>

<span data-ttu-id="ce69a-103">A causa di un bug in .NET Framework 4.5, i gestori eventi per gli eventi <xref:System.Windows.Controls.DataGrid> che includono la rimozione di una riga possono originare un'eccezione <xref:System.NullReferenceException?displayProperty=fullName> se accedono alle proprietà <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> o <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> di <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="ce69a-103">Due to a bug in the .NET Framework 4.5, event handlers for <xref:System.Windows.Controls.DataGrid> events involving the removal of a row can cause a <xref:System.NullReferenceException?displayProperty=fullName> to be thrown if they access the <xref:System.Windows.Controls.DataGrid>'s <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> or <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> properties.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ce69a-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="ce69a-104">Suggestion</span></span>

<span data-ttu-id="ce69a-105">Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ce69a-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="ce69a-106">Nome</span><span class="sxs-lookup"><span data-stu-id="ce69a-106">Name</span></span>    | <span data-ttu-id="ce69a-107">Valore</span><span class="sxs-lookup"><span data-stu-id="ce69a-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ce69a-108">Scope</span><span class="sxs-lookup"><span data-stu-id="ce69a-108">Scope</span></span>   |<span data-ttu-id="ce69a-109">Minorenne</span><span class="sxs-lookup"><span data-stu-id="ce69a-109">Minor</span></span>|
|<span data-ttu-id="ce69a-110">Version</span><span class="sxs-lookup"><span data-stu-id="ce69a-110">Version</span></span>|<span data-ttu-id="ce69a-111">4.5</span><span class="sxs-lookup"><span data-stu-id="ce69a-111">4.5</span></span>|
|<span data-ttu-id="ce69a-112">Type</span><span class="sxs-lookup"><span data-stu-id="ce69a-112">Type</span></span>|<span data-ttu-id="ce69a-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="ce69a-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ce69a-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="ce69a-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
