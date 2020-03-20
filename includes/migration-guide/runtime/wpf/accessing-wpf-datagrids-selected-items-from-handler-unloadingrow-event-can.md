---
ms.openlocfilehash: cda5df4b673412a7c8c59f80f89c19c13dc81dc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858388"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a><span data-ttu-id="7af3a-101">L'accesso agli elementi selezionati di un elemento DataGrid WPF da parte di un gestore dell'evento UnloadingRow di DataGrid può determinare un'eccezione NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="7af3a-101">Accessing a WPF DataGrid's selected items from a handler of the DataGrid's UnloadingRow event can cause a NullReferenceException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7af3a-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7af3a-102">Details</span></span>|<span data-ttu-id="7af3a-103">A causa di un bug in .NET Framework 4.5, i gestori eventi per gli eventi <xref:System.Windows.Controls.DataGrid> che includono la rimozione di una riga possono originare un'eccezione <xref:System.NullReferenceException?displayProperty=name> se accedono alle proprietà <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> o <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> di <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="7af3a-103">Due to a bug in the .NET Framework 4.5, event handlers for <xref:System.Windows.Controls.DataGrid> events involving the removal of a row can cause a <xref:System.NullReferenceException?displayProperty=name> to be thrown if they access the <xref:System.Windows.Controls.DataGrid>'s <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> or <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> properties.</span></span>|
|<span data-ttu-id="7af3a-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="7af3a-104">Suggestion</span></span>|<span data-ttu-id="7af3a-105">Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7af3a-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="7af3a-106">Scope</span><span class="sxs-lookup"><span data-stu-id="7af3a-106">Scope</span></span>|<span data-ttu-id="7af3a-107">Minorenne</span><span class="sxs-lookup"><span data-stu-id="7af3a-107">Minor</span></span>|
|<span data-ttu-id="7af3a-108">Versione</span><span class="sxs-lookup"><span data-stu-id="7af3a-108">Version</span></span>|<span data-ttu-id="7af3a-109">4.5</span><span class="sxs-lookup"><span data-stu-id="7af3a-109">4.5</span></span>|
|<span data-ttu-id="7af3a-110">Type</span><span class="sxs-lookup"><span data-stu-id="7af3a-110">Type</span></span>|<span data-ttu-id="7af3a-111">Runtime</span><span class="sxs-lookup"><span data-stu-id="7af3a-111">Runtime</span></span>|
|<span data-ttu-id="7af3a-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="7af3a-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
