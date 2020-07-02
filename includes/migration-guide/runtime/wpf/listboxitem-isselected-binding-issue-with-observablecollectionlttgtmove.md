---
ms.openlocfilehash: f4ff938b2d0e9ead481fdf239aed8a6b918a99b0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620449"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a><span data-ttu-id="f84e3-101">Problema di associazione ListBoxItem IsSelected con ObservableCollection&lt;T&gt;.Move</span><span class="sxs-lookup"><span data-stu-id="f84e3-101">ListBoxItem IsSelected binding issue with ObservableCollection&lt;T&gt;.Move</span></span>

#### <a name="details"></a><span data-ttu-id="f84e3-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f84e3-102">Details</span></span>

<span data-ttu-id="f84e3-103">La chiamata di <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> oppure <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> su una raccolta associata a un controllo <xref:System.Windows.Controls.ListBox?displayProperty=fullName> con elementi selezionati può causare un comportamento imprevedibile per la selezione futura o la deselezione di elementi <xref:System.Windows.Controls.ListBox?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f84e3-103">Calling <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> or <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> on a collection bound to a <xref:System.Windows.Controls.ListBox?displayProperty=fullName> with items selected can lead to erratic behavior with future selection or unselection of <xref:System.Windows.Controls.ListBox?displayProperty=fullName> items.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f84e3-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="f84e3-104">Suggestion</span></span>

<span data-ttu-id="f84e3-105">La chiamata di <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> e <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> invece di <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> risolverà questo problema.</span><span class="sxs-lookup"><span data-stu-id="f84e3-105">Calling <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> and <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> instead of <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> will work around this issue.</span></span> <span data-ttu-id="f84e3-106">In alternativa, questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f84e3-106">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="f84e3-107">Nome</span><span class="sxs-lookup"><span data-stu-id="f84e3-107">Name</span></span>    | <span data-ttu-id="f84e3-108">Valore</span><span class="sxs-lookup"><span data-stu-id="f84e3-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f84e3-109">Scope</span><span class="sxs-lookup"><span data-stu-id="f84e3-109">Scope</span></span>   |<span data-ttu-id="f84e3-110">Minorenne</span><span class="sxs-lookup"><span data-stu-id="f84e3-110">Minor</span></span>|
|<span data-ttu-id="f84e3-111">Version</span><span class="sxs-lookup"><span data-stu-id="f84e3-111">Version</span></span>|<span data-ttu-id="f84e3-112">4.5</span><span class="sxs-lookup"><span data-stu-id="f84e3-112">4.5</span></span>|
|<span data-ttu-id="f84e3-113">Type</span><span class="sxs-lookup"><span data-stu-id="f84e3-113">Type</span></span>|<span data-ttu-id="f84e3-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="f84e3-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f84e3-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="f84e3-115">Affected APIs</span></span>

-<xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
