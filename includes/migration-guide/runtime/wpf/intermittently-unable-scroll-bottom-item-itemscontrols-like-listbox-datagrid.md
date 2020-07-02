---
ms.openlocfilehash: b92dc8a1c48e83846c3d9a1d86e66629f31b7722
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622021"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a><span data-ttu-id="842ca-101">Di tanti in tanto non è possibile scorrere fino all'elemento inferiore in ItemsControls (ad esempio ListBox e DataGrid) quando si usano DataTemplates personalizzati</span><span class="sxs-lookup"><span data-stu-id="842ca-101">Intermittently unable to scroll to bottom item in ItemsControls (like ListBox and DataGrid) when using custom DataTemplates</span></span>

#### <a name="details"></a><span data-ttu-id="842ca-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="842ca-102">Details</span></span>

<span data-ttu-id="842ca-103">In alcuni casi, a causa di un bug in .NET Framework 4.5 i controlli ItemsControls (come <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> e così via) non scorrono fino all'elemento inferiore quando si usano DataTemplates personalizzati.</span><span class="sxs-lookup"><span data-stu-id="842ca-103">In some instances, a bug in the .NET Framework 4.5 is causing ItemsControls (like <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>, etc.) to not scroll to their bottom item when using custom DataTemplates.</span></span> <span data-ttu-id="842ca-104">Lo scorrimento funzionerà se si esegue un secondo tentativo dopo uno scorrimento verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="842ca-104">If the scrolling is attempted a second time (after scrolling back up), it will work then.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="842ca-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="842ca-105">Suggestion</span></span>

<span data-ttu-id="842ca-106">Questo problema è stato corretto in .NET Framework 4.5.2 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework o a una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="842ca-106">This issue has been fixed in the .NET Framework 4.5.2 and may be addressed by upgrading to that version (or a later version) of the .NET Framework.</span></span> <span data-ttu-id="842ca-107">In alternativa, gli utenti possono trascinare le barre di scorrimento fino agli elementi finali di queste raccolte, ma potrebbe essere necessario provare due volte per completare l'operazione correttamente.</span><span class="sxs-lookup"><span data-stu-id="842ca-107">Alternatively, users can still drag scroll bars to the final items in these collections, but may need to try twice to do so successfully.</span></span>

| <span data-ttu-id="842ca-108">Nome</span><span class="sxs-lookup"><span data-stu-id="842ca-108">Name</span></span>    | <span data-ttu-id="842ca-109">Valore</span><span class="sxs-lookup"><span data-stu-id="842ca-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="842ca-110">Scope</span><span class="sxs-lookup"><span data-stu-id="842ca-110">Scope</span></span>   |<span data-ttu-id="842ca-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="842ca-111">Minor</span></span>|
|<span data-ttu-id="842ca-112">Version</span><span class="sxs-lookup"><span data-stu-id="842ca-112">Version</span></span>|<span data-ttu-id="842ca-113">4.5</span><span class="sxs-lookup"><span data-stu-id="842ca-113">4.5</span></span>|
|<span data-ttu-id="842ca-114">Type</span><span class="sxs-lookup"><span data-stu-id="842ca-114">Type</span></span>|<span data-ttu-id="842ca-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="842ca-115">Runtime</span></span>|
