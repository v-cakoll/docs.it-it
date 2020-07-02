---
ms.openlocfilehash: 5f1a8af37a305ab0904801002dd99e17e8eca62e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616122"
---
### <a name="two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a><span data-ttu-id="47265-101">Il data binding bidirezionale con una proprietà senza un setter pubblico non è supportato</span><span class="sxs-lookup"><span data-stu-id="47265-101">Two-way data-binding to a property with a non-public setter is not supported</span></span>

#### <a name="details"></a><span data-ttu-id="47265-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="47265-102">Details</span></span>

<span data-ttu-id="47265-103">Il data binding per una proprietà senza un setter pubblico non è mai stata uno scenario supportato.</span><span class="sxs-lookup"><span data-stu-id="47265-103">Attempting to data bind to a property without a public setter has never been a supported scenario.</span></span> <span data-ttu-id="47265-104">A partire da .NET Framework 4.5.1, questo scenario genererà una <xref:System.InvalidOperationException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="47265-104">Beginning in the .NET Framework 4.5.1, this scenario will throw an <xref:System.InvalidOperationException?displayProperty=fullName>.</span></span> <span data-ttu-id="47265-105">Si noti che la nuova eccezione verrà generata soltanto per le app destinate specificamente a .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="47265-105">Note that this new exception will only be thrown for apps that specifically target the .NET Framework 4.5.1.</span></span> <span data-ttu-id="47265-106">Per le app destinate a .NET Framework 4.5, la chiamata sarà consentita.</span><span class="sxs-lookup"><span data-stu-id="47265-106">If an app targets the .NET Framework 4.5, the call will be allowed.</span></span> <span data-ttu-id="47265-107">Se l'app non è destinata a una versione specifica di .NET Framework, l'associazione verrà considerata unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="47265-107">If the app does not target a particular .NET Framework version, the binding will be treated as one-way.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="47265-108">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="47265-108">Suggestion</span></span>

<span data-ttu-id="47265-109">È consigliabile aggiornare l'app per usare l'associazione unidirezionale o esporre pubblicamente il setter della proprietà.</span><span class="sxs-lookup"><span data-stu-id="47265-109">The app should be updated to either use one-way binding, or expose the property's setter publicly.</span></span> <span data-ttu-id="47265-110">In alternativa, è possibile destinare l'app a .NET Framework 4.5 per ottenere il comportamento precedente.</span><span class="sxs-lookup"><span data-stu-id="47265-110">Alternatively, targeting the .NET Framework 4.5 will cause the app to exhibit the old behavior.</span></span>

| <span data-ttu-id="47265-111">Nome</span><span class="sxs-lookup"><span data-stu-id="47265-111">Name</span></span>    | <span data-ttu-id="47265-112">Valore</span><span class="sxs-lookup"><span data-stu-id="47265-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="47265-113">Scope</span><span class="sxs-lookup"><span data-stu-id="47265-113">Scope</span></span>   | <span data-ttu-id="47265-114">Minorenne</span><span class="sxs-lookup"><span data-stu-id="47265-114">Minor</span></span>       |
| <span data-ttu-id="47265-115">Version</span><span class="sxs-lookup"><span data-stu-id="47265-115">Version</span></span> | <span data-ttu-id="47265-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="47265-116">4.5.1</span></span>       |
| <span data-ttu-id="47265-117">Type</span><span class="sxs-lookup"><span data-stu-id="47265-117">Type</span></span>    | <span data-ttu-id="47265-118">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="47265-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="47265-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="47265-119">Affected APIs</span></span>

- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>
