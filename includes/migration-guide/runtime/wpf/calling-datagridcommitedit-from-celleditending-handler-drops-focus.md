---
ms.openlocfilehash: c3c3ed44cf53625c246dfe0408bb861750ecf336
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622025"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a><span data-ttu-id="7692c-101">La chiamata di DataGrid.CommitEdit da un gestore CellEditEnding fa perdere lo stato attivo</span><span class="sxs-lookup"><span data-stu-id="7692c-101">Calling DataGrid.CommitEdit from a CellEditEnding handler drops focus</span></span>

#### <a name="details"></a><span data-ttu-id="7692c-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7692c-102">Details</span></span>

<span data-ttu-id="7692c-103">La chiamata di <xref:System.Windows.Controls.DataGrid.CommitEdit> da uno dei gestori eventi <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> di <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> causa la perdita dello stato attivo per <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="7692c-103">Calling <xref:System.Windows.Controls.DataGrid.CommitEdit> from one of the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>'s <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> event handlers causes the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> to lose focus.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7692c-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="7692c-104">Suggestion</span></span>

<span data-ttu-id="7692c-105">Questo bug è stato risolto in .NET Framework 4.5.2, pertanto può essere evitato eseguendo l'aggiornamento di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7692c-105">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="7692c-106">In alternativa, è possibile evitarlo selezionando di nuovo in modo esplicito <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> dopo la chiamata di <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="7692c-106">Alternatively, it can be avoided by explicitly re-selecting the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> after calling <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.</span></span>

| <span data-ttu-id="7692c-107">Nome</span><span class="sxs-lookup"><span data-stu-id="7692c-107">Name</span></span>    | <span data-ttu-id="7692c-108">Valore</span><span class="sxs-lookup"><span data-stu-id="7692c-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7692c-109">Scope</span><span class="sxs-lookup"><span data-stu-id="7692c-109">Scope</span></span>   |<span data-ttu-id="7692c-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7692c-110">Edge</span></span>|
|<span data-ttu-id="7692c-111">Version</span><span class="sxs-lookup"><span data-stu-id="7692c-111">Version</span></span>|<span data-ttu-id="7692c-112">4.5</span><span class="sxs-lookup"><span data-stu-id="7692c-112">4.5</span></span>|
|<span data-ttu-id="7692c-113">Type</span><span class="sxs-lookup"><span data-stu-id="7692c-113">Type</span></span>|<span data-ttu-id="7692c-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="7692c-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7692c-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="7692c-115">Affected APIs</span></span>

-<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|
