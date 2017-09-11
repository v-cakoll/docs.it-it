---
title: readonly (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- readonly_CSharpKeyword
- readonly
dev_langs:
- CSharp
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: 16
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
ms.openlocfilehash: 2660aa56721815cbbeb668328863956473cce8f1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="readonly-c-reference"></a><span data-ttu-id="218e6-102">readonly (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="218e6-102">readonly (C# Reference)</span></span>
<span data-ttu-id="218e6-103">La parola chiave `readonly` è un modificatore utilizzabile nei campi.</span><span class="sxs-lookup"><span data-stu-id="218e6-103">The `readonly` keyword is a modifier that you can use on fields.</span></span> <span data-ttu-id="218e6-104">Quando una dichiarazione di campo include un modificatore `readonly`, le assegnazioni ai campi introdotte dalla dichiarazione possono verificarsi solo come parte della dichiarazione o in un costruttore della stessa classe.</span><span class="sxs-lookup"><span data-stu-id="218e6-104">When a field declaration includes a `readonly` modifier, assignments to the fields introduced by the declaration can only occur as part of the declaration or in a constructor in the same class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="218e6-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="218e6-105">Example</span></span>  
 <span data-ttu-id="218e6-106">In questo esempio, il valore del campo `year` non può essere modificato nel metodo `ChangeYear`, anche se gli viene assegnato un valore nel costruttore della classe:</span><span class="sxs-lookup"><span data-stu-id="218e6-106">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>  
  
 <span data-ttu-id="218e6-107">[!code-cs[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="218e6-107">[!code-cs[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]</span></span>  
  
 <span data-ttu-id="218e6-108">È possibile assegnare un valore a un campo `readonly` solo nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="218e6-108">You can assign a value to a `readonly` field only in the following contexts:</span></span>  
  
-   <span data-ttu-id="218e6-109">Quando la variabile viene inizializzata nella dichiarazione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="218e6-109">When the variable is initialized in the declaration, for example:</span></span>  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   <span data-ttu-id="218e6-110">Per un campo di istanza, nei costruttori di istanza della classe che contiene la dichiarazione del campo, o per un campo statico, nel costruttore statico della classe che contiene la dichiarazione del campo.</span><span class="sxs-lookup"><span data-stu-id="218e6-110">For an instance field, in the instance constructors of the class that contains the field declaration, or for a static field, in the static constructor of the class that contains the field declaration.</span></span> <span data-ttu-id="218e6-111">Questi sono anche gli unici contesti in cui è possibile passare un campo `readonly` come parametro [out](../../../csharp/language-reference/keywords/out.md) o [ref](../../../csharp/language-reference/keywords/ref.md).</span><span class="sxs-lookup"><span data-stu-id="218e6-111">These are also the only contexts in which it is valid to pass a `readonly` field as an [out](../../../csharp/language-reference/keywords/out.md) or [ref](../../../csharp/language-reference/keywords/ref.md) parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="218e6-112">La parola chiave `readonly` è diversa dalla parola chiave [const](../../../csharp/language-reference/keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="218e6-112">The `readonly` keyword is different from the [const](../../../csharp/language-reference/keywords/const.md) keyword.</span></span> <span data-ttu-id="218e6-113">Un campo `const` può essere inizializzato solo nella dichiarazione del campo.</span><span class="sxs-lookup"><span data-stu-id="218e6-113">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="218e6-114">Un campo `readonly` può essere inizializzato nella dichiarazione o in un costruttore.</span><span class="sxs-lookup"><span data-stu-id="218e6-114">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="218e6-115">I campi `readonly` possono quindi presentare valori diversi a seconda del costruttore usato.</span><span class="sxs-lookup"><span data-stu-id="218e6-115">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="218e6-116">Inoltre, mentre un campo `const` rappresenta una costante in fase di compilazione, il campo `readonly` può essere usato per le costanti in fase di esecuzione, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="218e6-116">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="example"></a><span data-ttu-id="218e6-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="218e6-117">Example</span></span>  
 <span data-ttu-id="218e6-118">[!code-cs[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="218e6-118">[!code-cs[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]</span></span>  
  
 <span data-ttu-id="218e6-119">Nell'esempio precedente, se si usa un'istruzione simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="218e6-119">In the preceding example, if you use a statement like this:</span></span>  
  
 `p2.y = 66;        // Error`  
  
 <span data-ttu-id="218e6-120">si otterrà il messaggio di errore del compilatore:</span><span class="sxs-lookup"><span data-stu-id="218e6-120">you will get the compiler error message:</span></span>  
  
 `The left-hand side of an assignment must be an l-value`  
  
 <span data-ttu-id="218e6-121">ovvero lo stesso errore che si ottiene quando si tenta di assegnare un valore a una costante.</span><span class="sxs-lookup"><span data-stu-id="218e6-121">which is the same error you get when you attempt to assign a value to a constant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="218e6-122">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="218e6-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="218e6-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="218e6-123">See Also</span></span>  
 <span data-ttu-id="218e6-124">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="218e6-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="218e6-125">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="218e6-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="218e6-126">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="218e6-126">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="218e6-127">[Modificatori](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="218e6-127">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="218e6-128">[const](../../../csharp/language-reference/keywords/const.md) </span><span class="sxs-lookup"><span data-stu-id="218e6-128">[const](../../../csharp/language-reference/keywords/const.md) </span></span>  
 [<span data-ttu-id="218e6-129">Campi</span><span class="sxs-lookup"><span data-stu-id="218e6-129">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)

