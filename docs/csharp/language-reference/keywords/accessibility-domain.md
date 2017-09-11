---
title: "Dominio di accessibilità (Riferimenti per C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 90faf22d8a7d515ae8bd062f0b95f4be5e051f79
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="6dad7-102">Dominio di accessibilità (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="6dad7-102">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="6dad7-103">Il dominio di accessibilità di un membro specifica in quali sezioni del programma è possibile fare riferimento a un membro.</span><span class="sxs-lookup"><span data-stu-id="6dad7-103">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="6dad7-104">Se il membro è annidato all'interno di un altro tipo, il suo dominio di accessibilità viene determinato dal [livello di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md) del membro e dal dominio di accessibilità del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="6dad7-104">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](../../../csharp/language-reference/keywords/accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="6dad7-105">Il dominio di accessibilità di un tipo di primo livello è minimo il testo di programma del progetto in cui è dichiarato.</span><span class="sxs-lookup"><span data-stu-id="6dad7-105">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="6dad7-106">Vale a dire che il dominio include tutti i file di origine di questo progetto.</span><span class="sxs-lookup"><span data-stu-id="6dad7-106">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="6dad7-107">Il dominio di accessibilità di un tipo annidato è minimo il testo del programma del tipo in cui è dichiarato.</span><span class="sxs-lookup"><span data-stu-id="6dad7-107">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="6dad7-108">Vale a dire che il dominio è il corpo tipo che include tutti i tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="6dad7-108">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="6dad7-109">Il dominio di accessibilità di un tipo annidato non è mai superiore a quello del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="6dad7-109">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="6dad7-110">Questi concetti vengono illustrati nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6dad7-110">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6dad7-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="6dad7-111">Example</span></span>  
 <span data-ttu-id="6dad7-112">Questo esempio include un tipo di primo livello, `T1`, e due classi annidate, `M1` e `M2`.</span><span class="sxs-lookup"><span data-stu-id="6dad7-112">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="6dad7-113">Le classi contengono campi diversi con accessibilità dichiarate.</span><span class="sxs-lookup"><span data-stu-id="6dad7-113">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="6dad7-114">Nel metodo `Main` un commento segue ogni istruzione per indicare il dominio di accessibilità di ogni membro.</span><span class="sxs-lookup"><span data-stu-id="6dad7-114">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="6dad7-115">Si noti che le istruzioni che fanno riferimento ai membri non accessibili includono un commento.</span><span class="sxs-lookup"><span data-stu-id="6dad7-115">Notice that the statements that try to reference the inaccessible members are commented out.</span></span> <span data-ttu-id="6dad7-116">Per rivedere gli errori di compilazione generati dal riferimento a un membro inaccessibile, rimuovere i commenti uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="6dad7-116">If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
 <span data-ttu-id="6dad7-117">[!code-cs[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6dad7-117">[!code-cs[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6dad7-118">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="6dad7-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6dad7-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6dad7-119">See Also</span></span>  
 <span data-ttu-id="6dad7-120">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6dad7-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6dad7-121">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6dad7-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6dad7-122">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="6dad7-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="6dad7-123">[Modificatori di accesso](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="6dad7-123">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="6dad7-124">[Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="6dad7-124">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="6dad7-125">[Restrizioni relative all'uso dei livelli di accessibilità](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="6dad7-125">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span></span>  
 <span data-ttu-id="6dad7-126">[Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="6dad7-126">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="6dad7-127">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="6dad7-127">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="6dad7-128">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="6dad7-128">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="6dad7-129">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="6dad7-129">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 [<span data-ttu-id="6dad7-130">internal</span><span class="sxs-lookup"><span data-stu-id="6dad7-130">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

