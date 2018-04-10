---
title: Dominio di accessibilità (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 127bacda4bf8363fccff3dd3ef6770ad50984cfb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="a17c2-102">Dominio di accessibilità (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a17c2-102">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="a17c2-103">Il dominio di accessibilità di un membro specifica in quali sezioni del programma è possibile fare riferimento a un membro.</span><span class="sxs-lookup"><span data-stu-id="a17c2-103">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="a17c2-104">Se il membro è annidato all'interno di un altro tipo, il suo dominio di accessibilità viene determinato dal [livello di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md) del membro e dal dominio di accessibilità del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="a17c2-104">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](../../../csharp/language-reference/keywords/accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="a17c2-105">Il dominio di accessibilità di un tipo di primo livello è minimo il testo di programma del progetto in cui è dichiarato.</span><span class="sxs-lookup"><span data-stu-id="a17c2-105">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="a17c2-106">Vale a dire che il dominio include tutti i file di origine di questo progetto.</span><span class="sxs-lookup"><span data-stu-id="a17c2-106">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="a17c2-107">Il dominio di accessibilità di un tipo annidato è minimo il testo del programma del tipo in cui è dichiarato.</span><span class="sxs-lookup"><span data-stu-id="a17c2-107">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="a17c2-108">Vale a dire che il dominio è il corpo tipo che include tutti i tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="a17c2-108">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="a17c2-109">Il dominio di accessibilità di un tipo annidato non è mai superiore a quello del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="a17c2-109">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="a17c2-110">Questi concetti vengono illustrati nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a17c2-110">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a17c2-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="a17c2-111">Example</span></span>  
 <span data-ttu-id="a17c2-112">Questo esempio include un tipo di primo livello, `T1`, e due classi annidate, `M1` e `M2`.</span><span class="sxs-lookup"><span data-stu-id="a17c2-112">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="a17c2-113">Le classi contengono campi diversi con accessibilità dichiarate.</span><span class="sxs-lookup"><span data-stu-id="a17c2-113">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="a17c2-114">Nel metodo `Main` un commento segue ogni istruzione per indicare il dominio di accessibilità di ogni membro.</span><span class="sxs-lookup"><span data-stu-id="a17c2-114">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="a17c2-115">Si noti che le istruzioni che fanno riferimento ai membri non accessibili includono un commento. Per rivedere gli errori di compilazione generati dal riferimento a un membro inaccessibile, rimuovere i commenti uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="a17c2-115">Notice that the statements that try to reference the inaccessible members are commented out. If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="a17c2-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a17c2-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a17c2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a17c2-117">See Also</span></span>  
 [<span data-ttu-id="a17c2-118">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a17c2-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a17c2-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a17c2-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a17c2-120">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="a17c2-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="a17c2-121">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="a17c2-121">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="a17c2-122">Livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="a17c2-122">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="a17c2-123">Restrizioni relative all'uso dei livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="a17c2-123">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [<span data-ttu-id="a17c2-124">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="a17c2-124">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="a17c2-125">public</span><span class="sxs-lookup"><span data-stu-id="a17c2-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="a17c2-126">private</span><span class="sxs-lookup"><span data-stu-id="a17c2-126">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="a17c2-127">protected</span><span class="sxs-lookup"><span data-stu-id="a17c2-127">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="a17c2-128">internal</span><span class="sxs-lookup"><span data-stu-id="a17c2-128">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
