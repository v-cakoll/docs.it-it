---
ms.openlocfilehash: bae6d7c0f8843211c721c68ce6f16000b35b4401
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620458"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a><span data-ttu-id="ef824-101">Nuovi valori enumerazione in PageRangeSelection di WPF</span><span class="sxs-lookup"><span data-stu-id="ef824-101">New enum values in WPF's PageRangeSelection</span></span>

#### <a name="details"></a><span data-ttu-id="ef824-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ef824-102">Details</span></span>

<span data-ttu-id="ef824-103">Sono stati aggiunti due nuovi membri (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> e <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) all'enumerazione <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="ef824-103">Two new members (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> and <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) have been added to the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> enum.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ef824-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="ef824-104">Suggestion</span></span>

<span data-ttu-id="ef824-105">Nella maggior parte dei casi queste modifiche non influiscono sul codice utente.</span><span class="sxs-lookup"><span data-stu-id="ef824-105">In most cases, these changes won't impact user code.</span></span> <span data-ttu-id="ef824-106">È tuttavia consigliabile modificare il codice che dipende da un determinato numero di elementi esistenti nelle chiamate <xref:System.Enum.GetNames(System.Type)> o <xref:System.Enum.GetValues(System.Type)> per il tipo <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="ef824-106">Code that depends on a particular number of elements existing in <xref:System.Enum.GetNames(System.Type)> or <xref:System.Enum.GetValues(System.Type)> calls on the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> type should be modified, though.</span></span>

| <span data-ttu-id="ef824-107">Nome</span><span class="sxs-lookup"><span data-stu-id="ef824-107">Name</span></span>    | <span data-ttu-id="ef824-108">Valore</span><span class="sxs-lookup"><span data-stu-id="ef824-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ef824-109">Scope</span><span class="sxs-lookup"><span data-stu-id="ef824-109">Scope</span></span>   |<span data-ttu-id="ef824-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ef824-110">Edge</span></span>|
|<span data-ttu-id="ef824-111">Version</span><span class="sxs-lookup"><span data-stu-id="ef824-111">Version</span></span>|<span data-ttu-id="ef824-112">4.5</span><span class="sxs-lookup"><span data-stu-id="ef824-112">4.5</span></span>|
|<span data-ttu-id="ef824-113">Type</span><span class="sxs-lookup"><span data-stu-id="ef824-113">Type</span></span>|<span data-ttu-id="ef824-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="ef824-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ef824-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="ef824-115">Affected APIs</span></span>

-<xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
