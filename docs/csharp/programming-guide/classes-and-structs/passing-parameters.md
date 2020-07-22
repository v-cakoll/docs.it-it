---
title: Passaggio di parametri - Guida per programmatori C#
description: È possibile passare un argomento a un parametro in C# per valore o per riferimento. Le modifiche apportate a un argomento passato dal riferimento vengono mantenute. Usare ref o out per passare per riferimento.
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: 875a42aacf3d7aa4124684aefafdcb07ff4c87d6
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864735"
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="125eb-105">Passaggio di parametri (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="125eb-105">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="125eb-106">In C# è possibile passare gli argomenti ai parametri per valore o per riferimento.</span><span class="sxs-lookup"><span data-stu-id="125eb-106">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="125eb-107">Il passaggio per riferimento consente a membri di funzioni, metodi, proprietà, indicizzatori, operatori e costruttori di modificare il valore dei parametri e rendere permanenti le modifiche nell'ambiente chiamante.</span><span class="sxs-lookup"><span data-stu-id="125eb-107">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="125eb-108">Per passare un parametro per riferimento con l'intenzione di modificare il valore, usare la parola chiave `ref` o `out`.</span><span class="sxs-lookup"><span data-stu-id="125eb-108">To pass a parameter by reference with the intent of changing the value, use the `ref`, or `out` keyword.</span></span> <span data-ttu-id="125eb-109">Per passare per riferimento con l'intenzione di evitare la copia, ma non la modifica del valore, usare il modificatore `in`.</span><span class="sxs-lookup"><span data-stu-id="125eb-109">To pass by reference with the intent of avoiding copying but not changing the value, use the `in` modifier.</span></span> <span data-ttu-id="125eb-110">Per semplicità, negli esempi riportati in questo argomento verrà utilizzata soltanto la parola chiave `ref`.</span><span class="sxs-lookup"><span data-stu-id="125eb-110">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="125eb-111">Per altre informazioni sulla differenza tra `in`, `ref` e `out`, vedere [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md) e [out](../../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="125eb-111">For more information about the difference between `in`, `ref`, and `out`, see [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), and [out](../../language-reference/keywords/out-parameter-modifier.md).</span></span>  
  
 <span data-ttu-id="125eb-112">L'esempio seguente illustra la differenza fra parametri di valore e di riferimento.</span><span class="sxs-lookup"><span data-stu-id="125eb-112">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#10)]  
  
 <span data-ttu-id="125eb-113">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="125eb-113">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="125eb-114">Passaggio di parametri di tipi di valore</span><span class="sxs-lookup"><span data-stu-id="125eb-114">Passing Value-Type Parameters</span></span>](./passing-value-type-parameters.md)  
  
- [<span data-ttu-id="125eb-115">Passaggio di parametri di tipo di riferimento</span><span class="sxs-lookup"><span data-stu-id="125eb-115">Passing Reference-Type Parameters</span></span>](./passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="125eb-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="125eb-116">C# Language Specification</span></span>  

<span data-ttu-id="125eb-117">Per altre informazioni, vedere [Elenchi di argomenti](~/_csharplang/spec/expressions.md#argument-lists) nella [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="125eb-117">For more information, see [Argument lists](~/_csharplang/spec/expressions.md#argument-lists) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="125eb-118">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="125eb-118">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="125eb-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="125eb-119">See also</span></span>

- [<span data-ttu-id="125eb-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="125eb-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="125eb-121">Metodi</span><span class="sxs-lookup"><span data-stu-id="125eb-121">Methods</span></span>](./methods.md)
