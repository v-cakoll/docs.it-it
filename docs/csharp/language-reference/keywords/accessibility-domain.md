---
title: Dominio di accessibilità - Riferimenti per C#
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 4a4319b03f3e0d7f9ec721e611b78c124a8a8ee5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713827"
---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="edc97-102">Dominio di accessibilità (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="edc97-102">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="edc97-103">Il dominio di accessibilità di un membro specifica in quali sezioni del programma è possibile fare riferimento a un membro.</span><span class="sxs-lookup"><span data-stu-id="edc97-103">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="edc97-104">Se il membro è annidato all'interno di un altro tipo, il suo dominio di accessibilità viene determinato dal [livello di accessibilità](./accessibility-levels.md) del membro e dal dominio di accessibilità del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="edc97-104">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](./accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="edc97-105">Il dominio di accessibilità di un tipo di primo livello è minimo il testo di programma del progetto in cui è dichiarato.</span><span class="sxs-lookup"><span data-stu-id="edc97-105">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="edc97-106">Vale a dire che il dominio include tutti i file di origine di questo progetto.</span><span class="sxs-lookup"><span data-stu-id="edc97-106">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="edc97-107">Il dominio di accessibilità di un tipo annidato è minimo il testo del programma del tipo in cui è dichiarato.</span><span class="sxs-lookup"><span data-stu-id="edc97-107">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="edc97-108">Vale a dire che il dominio è il corpo tipo che include tutti i tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="edc97-108">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="edc97-109">Il dominio di accessibilità di un tipo annidato non è mai superiore a quello del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="edc97-109">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="edc97-110">Questi concetti vengono illustrati nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="edc97-110">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edc97-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="edc97-111">Example</span></span>  
 <span data-ttu-id="edc97-112">Questo esempio include un tipo di primo livello, `T1`, e due classi annidate, `M1` e `M2`.</span><span class="sxs-lookup"><span data-stu-id="edc97-112">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="edc97-113">Le classi contengono campi diversi con accessibilità dichiarate.</span><span class="sxs-lookup"><span data-stu-id="edc97-113">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="edc97-114">Nel metodo `Main` un commento segue ogni istruzione per indicare il dominio di accessibilità di ogni membro.</span><span class="sxs-lookup"><span data-stu-id="edc97-114">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="edc97-115">Si noti che le istruzioni che tentano di fare riferimento ai membri inaccessibili sono impostate come commento. Se si desidera visualizzare gli errori del compilatore causati da un riferimento a un membro inaccessibile, rimuovere i commenti uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="edc97-115">Notice that the statements that try to reference the inaccessible members are commented out. If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a><span data-ttu-id="edc97-116">Specifica del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="edc97-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="edc97-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edc97-117">See also</span></span>

- [<span data-ttu-id="edc97-118">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="edc97-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="edc97-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="edc97-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="edc97-120">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="edc97-120">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="edc97-121">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="edc97-121">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="edc97-122">Livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="edc97-122">Accessibility Levels</span></span>](./accessibility-levels.md)
- [<span data-ttu-id="edc97-123">Restrizioni relative all'uso dei livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="edc97-123">Restrictions on Using Accessibility Levels</span></span>](./restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="edc97-124">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="edc97-124">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="edc97-125">public</span><span class="sxs-lookup"><span data-stu-id="edc97-125">public</span></span>](./public.md)
- [<span data-ttu-id="edc97-126">private</span><span class="sxs-lookup"><span data-stu-id="edc97-126">private</span></span>](./private.md)
- [<span data-ttu-id="edc97-127">protected</span><span class="sxs-lookup"><span data-stu-id="edc97-127">protected</span></span>](./protected.md)
- [<span data-ttu-id="edc97-128">internal</span><span class="sxs-lookup"><span data-stu-id="edc97-128">internal</span></span>](./internal.md)
