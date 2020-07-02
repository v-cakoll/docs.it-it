---
ms.openlocfilehash: 9a2d6a25a8ab1b8bf65b947557802e0805a7f826
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617201"
---
### <a name="foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a><span data-ttu-id="f1322-101">L'ambito della variabile iteratore Foreach è ora all'interno dell'iterazione, quindi la semantica di acquisizione della chiusura è diversa (in C# 5)</span><span class="sxs-lookup"><span data-stu-id="f1322-101">Foreach iterator variable is now scoped within the iteration, so closure capturing semantics are different (in C#5)</span></span>

#### <a name="details"></a><span data-ttu-id="f1322-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f1322-102">Details</span></span>

<span data-ttu-id="f1322-103">A partire da C# 5 (Visual Studio 2012), le variabili iteratore `foreach` hanno ambito limitato all'interno dell'iterazione.</span><span class="sxs-lookup"><span data-stu-id="f1322-103">Beginning with C# 5 (Visual Studio 2012), `foreach` iterator variables are scoped within the iteration.</span></span> <span data-ttu-id="f1322-104">Ciò può causare interruzioni se il codice dipende dal fatto che le variabili non siano incluse nella chiusura di `foreach`.</span><span class="sxs-lookup"><span data-stu-id="f1322-104">This can cause breaks if code was previously depending on the variables to not be included in the `foreach`'s closure.</span></span> <span data-ttu-id="f1322-105">Il sintomo di questa modifica è che una variabile iteratore passata a un delegato viene gestita come avente il valore esistente al momento della creazione del delegato, invece del valore esistente al momento della chiamata del delegato.</span><span class="sxs-lookup"><span data-stu-id="f1322-105">The symptom of this change is that an iterator variable passed to a delegate is treated as the value it has at the time the delegate is created, rather than the value it has at the time the delegate is invoked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f1322-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="f1322-106">Suggestion</span></span>

<span data-ttu-id="f1322-107">Idealmente, è consigliabile aggiornare il codice in modo che tenga conto del nuovo comportamento del compilatore.</span><span class="sxs-lookup"><span data-stu-id="f1322-107">Ideally, code should be updated to expect the new compiler behavior.</span></span> <span data-ttu-id="f1322-108">Se è richiesta la semantica precedente, la variabile iteratore può essere sostituita con una variabile separata che viene inserita in modo esplicito all'esterno dell'ambito del ciclo.</span><span class="sxs-lookup"><span data-stu-id="f1322-108">If the old semantics are required, the iterator variable can be replaced with a separate variable which is explicitly placed outside of the loop's scope.</span></span>

| <span data-ttu-id="f1322-109">Nome</span><span class="sxs-lookup"><span data-stu-id="f1322-109">Name</span></span>    | <span data-ttu-id="f1322-110">Valore</span><span class="sxs-lookup"><span data-stu-id="f1322-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f1322-111">Scope</span><span class="sxs-lookup"><span data-stu-id="f1322-111">Scope</span></span>   | <span data-ttu-id="f1322-112">Principale</span><span class="sxs-lookup"><span data-stu-id="f1322-112">Major</span></span>       |
| <span data-ttu-id="f1322-113">Version</span><span class="sxs-lookup"><span data-stu-id="f1322-113">Version</span></span> | <span data-ttu-id="f1322-114">4.5</span><span class="sxs-lookup"><span data-stu-id="f1322-114">4.5</span></span>         |
| <span data-ttu-id="f1322-115">Type</span><span class="sxs-lookup"><span data-stu-id="f1322-115">Type</span></span>    | <span data-ttu-id="f1322-116">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="f1322-116">Retargeting</span></span> |
