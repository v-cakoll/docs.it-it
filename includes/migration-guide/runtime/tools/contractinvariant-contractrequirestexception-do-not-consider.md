---
ms.openlocfilehash: 29c66edfeb1690199aac39b9c3076d161b2075d4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621343"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a><span data-ttu-id="62991-101">Contract.Invariant o Contract.Requires\<TException> non considera pure IsNullOrEmpty</span><span class="sxs-lookup"><span data-stu-id="62991-101">Contract.Invariant or Contract.Requires\<TException> do not consider String.IsNullOrEmpty to be pure</span></span>

#### <a name="details"></a><span data-ttu-id="62991-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="62991-102">Details</span></span>

<span data-ttu-id="62991-103">Per le app destinate a .NET Framework 4.6.1, se il contratto invariante per <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> o il contratto di precondizione per <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> chiama il <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> metodo, il rewriter genera l'avviso del compilatore CC1036: &quot; chiamata rilevata al metodo ' System. String. IsNullOrWhteSpace (System. String)' senza [pure] nel metodo. &quot; Si tratta di un avviso del compilatore invece di un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="62991-103">For apps that target the .NET Framework 4.6.1, if the invariant contract for <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> or the precondition contract for <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> calls the <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> method, the rewriter emits compiler warning CC1036: &quot;Detected call to method 'System.String.IsNullOrWhteSpace(System.String)' without [Pure] in method.&quot; This is a compiler warning rather than a compiler error.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="62991-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="62991-104">Suggestion</span></span>

<span data-ttu-id="62991-105">Questo comportamento è stato affrontato nel [problema GitHub n. 339](https://github.com/Microsoft/CodeContracts/issues/339).</span><span class="sxs-lookup"><span data-stu-id="62991-105">This behavior was addressed in [GitHub Issue #339](https://github.com/Microsoft/CodeContracts/issues/339).</span></span> <span data-ttu-id="62991-106">Per eliminare questo avviso, è possibile scaricare e compilare una versione aggiornata del codice sorgente per lo strumento Contratti di codice da [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md).</span><span class="sxs-lookup"><span data-stu-id="62991-106">To eliminate this warning, you can download and compile an updated version of the source code for the Code Contracts tool from [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md).</span></span> <span data-ttu-id="62991-107">Le informazioni per il download sono disponibili in fondo alla pagina.</span><span class="sxs-lookup"><span data-stu-id="62991-107">Download information is found at the bottom of the page.</span></span>

| <span data-ttu-id="62991-108">Nome</span><span class="sxs-lookup"><span data-stu-id="62991-108">Name</span></span>    | <span data-ttu-id="62991-109">Valore</span><span class="sxs-lookup"><span data-stu-id="62991-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="62991-110">Scope</span><span class="sxs-lookup"><span data-stu-id="62991-110">Scope</span></span>   |<span data-ttu-id="62991-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="62991-111">Minor</span></span>|
|<span data-ttu-id="62991-112">Version</span><span class="sxs-lookup"><span data-stu-id="62991-112">Version</span></span>|<span data-ttu-id="62991-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="62991-113">4.6.1</span></span>|
|<span data-ttu-id="62991-114">Type</span><span class="sxs-lookup"><span data-stu-id="62991-114">Type</span></span>|<span data-ttu-id="62991-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="62991-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="62991-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="62991-116">Affected APIs</span></span>

-<xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType></li></ul>|
