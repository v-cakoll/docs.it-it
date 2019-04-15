---
title: Dominio di accessibilità - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 529d256a553c4000c77bcd5096db1a4d943874ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141752"
---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="4e665-102">Dominio di accessibilità (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4e665-102">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="4e665-103">Il dominio di accessibilità di un membro specifica in quali sezioni del programma è possibile fare riferimento a un membro.</span><span class="sxs-lookup"><span data-stu-id="4e665-103">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="4e665-104">Se il membro è annidato all'interno di un altro tipo, il suo dominio di accessibilità viene determinato dal [livello di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md) del membro e dal dominio di accessibilità del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="4e665-104">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](../../../csharp/language-reference/keywords/accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="4e665-105">Il dominio di accessibilità di un tipo di primo livello è minimo il testo di programma del progetto in cui è dichiarato.</span><span class="sxs-lookup"><span data-stu-id="4e665-105">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="4e665-106">Vale a dire che il dominio include tutti i file di origine di questo progetto.</span><span class="sxs-lookup"><span data-stu-id="4e665-106">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="4e665-107">Il dominio di accessibilità di un tipo annidato è minimo il testo del programma del tipo in cui è dichiarato.</span><span class="sxs-lookup"><span data-stu-id="4e665-107">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="4e665-108">Vale a dire che il dominio è il corpo tipo che include tutti i tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="4e665-108">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="4e665-109">Il dominio di accessibilità di un tipo annidato non è mai superiore a quello del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="4e665-109">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="4e665-110">Questi concetti vengono illustrati nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4e665-110">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e665-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="4e665-111">Example</span></span>  
 <span data-ttu-id="4e665-112">Questo esempio include un tipo di primo livello, `T1`, e due classi annidate, `M1` e `M2`.</span><span class="sxs-lookup"><span data-stu-id="4e665-112">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="4e665-113">Le classi contengono campi diversi con accessibilità dichiarate.</span><span class="sxs-lookup"><span data-stu-id="4e665-113">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="4e665-114">Nel metodo `Main` un commento segue ogni istruzione per indicare il dominio di accessibilità di ogni membro.</span><span class="sxs-lookup"><span data-stu-id="4e665-114">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="4e665-115">Si noti che le istruzioni che fanno riferimento ai membri non accessibili includono un commento. Per rivedere gli errori di compilazione generati dal riferimento a un membro inaccessibile, rimuovere i commenti uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="4e665-115">Notice that the statements that try to reference the inaccessible members are commented out. If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a><span data-ttu-id="4e665-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="4e665-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4e665-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e665-117">See also</span></span>

- [<span data-ttu-id="4e665-118">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="4e665-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="4e665-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4e665-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4e665-120">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="4e665-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="4e665-121">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="4e665-121">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)
- [<span data-ttu-id="4e665-122">Livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="4e665-122">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)
- [<span data-ttu-id="4e665-123">Restrizioni relative all'uso dei livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="4e665-123">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="4e665-124">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="4e665-124">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="4e665-125">public</span><span class="sxs-lookup"><span data-stu-id="4e665-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)
- [<span data-ttu-id="4e665-126">private</span><span class="sxs-lookup"><span data-stu-id="4e665-126">private</span></span>](../../../csharp/language-reference/keywords/private.md)
- [<span data-ttu-id="4e665-127">protected</span><span class="sxs-lookup"><span data-stu-id="4e665-127">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
- [<span data-ttu-id="4e665-128">internal</span><span class="sxs-lookup"><span data-stu-id="4e665-128">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
