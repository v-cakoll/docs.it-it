---
title: extern alias (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: a2803d09ee64af854cad352f6a158fb84bb6d410
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2018
ms.locfileid: "37960587"
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="93485-102">extern alias (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="93485-102">extern alias (C# Reference)</span></span>
<span data-ttu-id="93485-103">È necessario far riferimento a due versioni di assembly che dispongono degli stessi nomi di tipo completi.</span><span class="sxs-lookup"><span data-stu-id="93485-103">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="93485-104">Ad esempio, potrebbe essere necessario usare due o più versioni di un assembly nella stessa applicazione.</span><span class="sxs-lookup"><span data-stu-id="93485-104">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="93485-105">Con un alias di assembly esterno, è possibile eseguire il wrapping degli spazi dei nomi di ogni assembly all'interno degli spazi dei nomi a livello radice denominati dall'alias, consentendone l'utilizzo nello stesso file.</span><span class="sxs-lookup"><span data-stu-id="93485-105">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93485-106">La parola chiave [extern](../../../csharp/language-reference/keywords/extern.md) viene anche usata come modificatore di metodo, che dichiara un metodo scritto in codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="93485-106">The [extern](../../../csharp/language-reference/keywords/extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="93485-107">Per far riferimento a due assembly con gli stessi nomi di tipo completi, è necessario specificare un alias al prompt dei comandi, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="93485-107">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="93485-108">In questo modo vengono creati gli alias extern `GridV1` e `GridV2`.</span><span class="sxs-lookup"><span data-stu-id="93485-108">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="93485-109">Per usare questi alias all'interno di un programma, far riferimento a essi tramite la parola chiave `extern`.</span><span class="sxs-lookup"><span data-stu-id="93485-109">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="93485-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="93485-110">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="93485-111">Ogni dichiarazione di alias extern introduce uno spazio dei nomi aggiuntivo a livello radice che affianca lo spazio dei nomi globale, ma non si trova al suo interno.</span><span class="sxs-lookup"><span data-stu-id="93485-111">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="93485-112">In questo modo, è possibile far riferimento ai tipi di ogni assembly senza ambiguità, usando il nome completo che dispone di una radice nell'alias dello spazio dei nomi appropriato.</span><span class="sxs-lookup"><span data-stu-id="93485-112">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="93485-113">Nell'esempio precedente, l'oggetto `GridV1::Grid` rappresenta il controllo griglia dell'oggetto `grid.dll`, e `GridV2::Grid` rappresenta il controllo griglia dell'oggetto `grid20.dll`.</span><span class="sxs-lookup"><span data-stu-id="93485-113">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="93485-114">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="93485-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="93485-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93485-115">See Also</span></span>  
 [<span data-ttu-id="93485-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="93485-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="93485-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="93485-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="93485-118">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="93485-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="93485-119">Parole chiave per gli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="93485-119">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="93485-120">Operatore ::</span><span class="sxs-lookup"><span data-stu-id="93485-120">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [<span data-ttu-id="93485-121">-reference (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="93485-121">/reference (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)
