---
title: Passaggio di parametri - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: 60ac7a8d982e7788f07debce114896859385c8e2
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705470"
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="067f7-102">Passaggio di parametri (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="067f7-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="067f7-103">In C# è possibile passare gli argomenti ai parametri per valore o per riferimento.</span><span class="sxs-lookup"><span data-stu-id="067f7-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="067f7-104">Il passaggio per riferimento consente a membri di funzioni, metodi, proprietà, indicizzatori, operatori e costruttori di modificare il valore dei parametri e rendere permanenti le modifiche nell'ambiente chiamante.</span><span class="sxs-lookup"><span data-stu-id="067f7-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="067f7-105">Per passare un parametro per riferimento con l'intenzione di modificare il valore, usare la parola chiave `ref` o `out`.</span><span class="sxs-lookup"><span data-stu-id="067f7-105">To pass a parameter by reference with the intent of changing the value, use the `ref`, or `out` keyword.</span></span> <span data-ttu-id="067f7-106">Per passare per riferimento con l'intenzione di evitare la copia, ma non la modifica del valore, usare il modificatore `in`.</span><span class="sxs-lookup"><span data-stu-id="067f7-106">To pass by reference with the intent of avoiding copying but not changing the value, use the `in` modifier.</span></span> <span data-ttu-id="067f7-107">Per semplicità, negli esempi riportati in questo argomento verrà utilizzata soltanto la parola chiave `ref`.</span><span class="sxs-lookup"><span data-stu-id="067f7-107">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="067f7-108">Per altre informazioni sulla differenza tra `in`, `ref` e `out`, vedere [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md) e [out](../../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="067f7-108">For more information about the difference between `in`, `ref`, and `out`, see [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), and [out](../../language-reference/keywords/out-parameter-modifier.md).</span></span>  
  
 <span data-ttu-id="067f7-109">L'esempio seguente illustra la differenza fra parametri di valore e di riferimento.</span><span class="sxs-lookup"><span data-stu-id="067f7-109">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#10)]  
  
 <span data-ttu-id="067f7-110">Per altre informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="067f7-110">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="067f7-111">Passaggio di parametri di tipo di valore</span><span class="sxs-lookup"><span data-stu-id="067f7-111">Passing Value-Type Parameters</span></span>](./passing-value-type-parameters.md)  
  
- [<span data-ttu-id="067f7-112">Passaggio di parametri di tipo di riferimento</span><span class="sxs-lookup"><span data-stu-id="067f7-112">Passing Reference-Type Parameters</span></span>](./passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="067f7-113">Specifica del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="067f7-113">C# Language Specification</span></span>  

<span data-ttu-id="067f7-114">Per altre informazioni, vedere [Elenchi di argomenti](~/_csharplang/spec/expressions.md#argument-lists) nella [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="067f7-114">For more information, see [Argument lists](~/_csharplang/spec/expressions.md#argument-lists) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="067f7-115">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="067f7-115">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="067f7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="067f7-116">See also</span></span>

- [<span data-ttu-id="067f7-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="067f7-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="067f7-118">Metodi</span><span class="sxs-lookup"><span data-stu-id="067f7-118">Methods</span></span>](./methods.md)
