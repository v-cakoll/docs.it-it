---
ms.openlocfilehash: 1be68c2968d0eaa9024007bcf37abf9e44c36f1c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622056"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a><span data-ttu-id="9a19c-101">Lo scorrimento di un controllo TreeView WPF o ListBox raggruppato in un VirtualizingStackPanel può causare un blocco</span><span class="sxs-lookup"><span data-stu-id="9a19c-101">Scrolling a WPF TreeView or grouped ListBox in a VirtualizingStackPanel can cause a hang</span></span>

#### <a name="details"></a><span data-ttu-id="9a19c-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9a19c-102">Details</span></span>

<span data-ttu-id="9a19c-103">In .NET Framework 4.5, lo scorrimento di un controllo <xref:System.Windows.Controls.TreeView?displayProperty=fullName> WPF in un pannello Stack virtualizzato può causare blocchi se sono presenti margini nel viewport (tra gli elementi nel controllo <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, ad esempio, o in un elemento ItemsPresenter).</span><span class="sxs-lookup"><span data-stu-id="9a19c-103">In the .NET Framework v4.5, scrolling a WPF <xref:System.Windows.Controls.TreeView?displayProperty=fullName> in a virtualized stack panel can cause hangs if there are margins in the viewport (between the items in the <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, for example, or on an ItemsPresenter element).</span></span> <span data-ttu-id="9a19c-104">In alcuni casi, inoltre, elementi di dimensioni diverse nella visualizzazione possono causare instabilità anche se non sono presenti margini.</span><span class="sxs-lookup"><span data-stu-id="9a19c-104">Additionally, in some cases, different sized items in the view can cause instability even if there are no margins.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9a19c-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="9a19c-105">Suggestion</span></span>

<span data-ttu-id="9a19c-106">È possibile evitare questo bug eseguendo l'aggiornamento a .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="9a19c-106">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="9a19c-107">In alternativa, i margini possono essere rimossi dalle raccolte di visualizzazioni (ad esempio <xref:System.Windows.Controls.TreeView?displayProperty=fullName>) all'interno di pannelli Stack virtualizzati, se tutti gli elementi contenuti sono della stessa dimensione.</span><span class="sxs-lookup"><span data-stu-id="9a19c-107">Alternatively, margins can be removed from view collections (like <xref:System.Windows.Controls.TreeView?displayProperty=fullName>s) within virtualized stack panels if all contained items are the same size.</span></span>

| <span data-ttu-id="9a19c-108">Nome</span><span class="sxs-lookup"><span data-stu-id="9a19c-108">Name</span></span>    | <span data-ttu-id="9a19c-109">Valore</span><span class="sxs-lookup"><span data-stu-id="9a19c-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9a19c-110">Scope</span><span class="sxs-lookup"><span data-stu-id="9a19c-110">Scope</span></span>   |<span data-ttu-id="9a19c-111">Principale</span><span class="sxs-lookup"><span data-stu-id="9a19c-111">Major</span></span>|
|<span data-ttu-id="9a19c-112">Version</span><span class="sxs-lookup"><span data-stu-id="9a19c-112">Version</span></span>|<span data-ttu-id="9a19c-113">4.5</span><span class="sxs-lookup"><span data-stu-id="9a19c-113">4.5</span></span>|
|<span data-ttu-id="9a19c-114">Type</span><span class="sxs-lookup"><span data-stu-id="9a19c-114">Type</span></span>|<span data-ttu-id="9a19c-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="9a19c-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9a19c-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="9a19c-116">Affected APIs</span></span>

-<xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
