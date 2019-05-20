---
title: Metodo parziale - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 14bcd3329b6ca8e46f6c180c97174a561108d143
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633362"
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="1f743-102">Metodo parziale (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1f743-102">partial method (C# Reference)</span></span>

<span data-ttu-id="1f743-103">Un metodo parziale ha la firma definita in una parte di un tipo parziale e l'implementazione definita in un'altra parte del tipo.</span><span class="sxs-lookup"><span data-stu-id="1f743-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="1f743-104">I metodi parziali consentono a Progettazione classi di fornire gli hook del metodo, analoghi ai gestori eventi, che gli sviluppatori possono decidere se implementare o meno.</span><span class="sxs-lookup"><span data-stu-id="1f743-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="1f743-105">Se lo sviluppatore non fornisce un'implementazione, il compilatore rimuove la firma in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="1f743-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="1f743-106">Ai metodi parziali si applicano le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f743-106">The following conditions apply to partial methods:</span></span>

- <span data-ttu-id="1f743-107">Le firme nelle due parti del tipo parziale devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="1f743-107">Signatures in both parts of the partial type must match.</span></span>

- <span data-ttu-id="1f743-108">Il metodo deve restituire void.</span><span class="sxs-lookup"><span data-stu-id="1f743-108">The method must return void.</span></span>

- <span data-ttu-id="1f743-109">Non è consentito alcun modificatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="1f743-109">No access modifiers are allowed.</span></span> <span data-ttu-id="1f743-110">I metodi parziali sono implicitamente privati.</span><span class="sxs-lookup"><span data-stu-id="1f743-110">Partial methods are implicitly private.</span></span>

<span data-ttu-id="1f743-111">Nell'esempio seguente viene illustrato un metodo parziale definito in due parti di una classe parziale:</span><span class="sxs-lookup"><span data-stu-id="1f743-111">The following example shows a partial method defined in two parts of a partial class:</span></span>

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

<span data-ttu-id="1f743-112">Per altre informazioni, vedere [Classi e metodi parziali](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="1f743-112">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1f743-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f743-113">See also</span></span>

- [<span data-ttu-id="1f743-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="1f743-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1f743-115">Tipo parziale</span><span class="sxs-lookup"><span data-stu-id="1f743-115">partial type</span></span>](partial-type.md)
