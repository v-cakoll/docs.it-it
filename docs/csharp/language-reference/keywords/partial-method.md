---
title: Metodo parziale - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 742d6ca744ac723179718f1400e600411712dd40
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238286"
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="cff42-102">Metodo parziale (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="cff42-102">partial method (C# Reference)</span></span>

<span data-ttu-id="cff42-103">Un metodo parziale ha la firma definita in una parte di un tipo parziale e l'implementazione definita in un'altra parte del tipo.</span><span class="sxs-lookup"><span data-stu-id="cff42-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="cff42-104">I metodi parziali consentono a Progettazione classi di fornire gli hook del metodo, analoghi ai gestori eventi, che gli sviluppatori possono decidere se implementare o meno.</span><span class="sxs-lookup"><span data-stu-id="cff42-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="cff42-105">Se lo sviluppatore non fornisce un'implementazione, il compilatore rimuove la firma in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="cff42-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="cff42-106">Ai metodi parziali si applicano le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cff42-106">The following conditions apply to partial methods:</span></span>

- <span data-ttu-id="cff42-107">Le firme nelle due parti del tipo parziale devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="cff42-107">Signatures in both parts of the partial type must match.</span></span>

- <span data-ttu-id="cff42-108">Il metodo deve restituire void.</span><span class="sxs-lookup"><span data-stu-id="cff42-108">The method must return void.</span></span>

- <span data-ttu-id="cff42-109">Non è consentito alcun modificatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="cff42-109">No access modifiers are allowed.</span></span> <span data-ttu-id="cff42-110">I metodi parziali sono implicitamente privati.</span><span class="sxs-lookup"><span data-stu-id="cff42-110">Partial methods are implicitly private.</span></span>

<span data-ttu-id="cff42-111">Nell'esempio seguente viene illustrato un metodo parziale definito in due parti di una classe parziale:</span><span class="sxs-lookup"><span data-stu-id="cff42-111">The following example shows a partial method defined in two parts of a partial class:</span></span>

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

<span data-ttu-id="cff42-112">Per altre informazioni, vedere [Classi e metodi parziali](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="cff42-112">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cff42-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cff42-113">See also</span></span>

- [<span data-ttu-id="cff42-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="cff42-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cff42-115">Tipo parziale</span><span class="sxs-lookup"><span data-stu-id="cff42-115">partial type</span></span>](partial-type.md)