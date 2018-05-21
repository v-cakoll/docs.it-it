---
title: readonly (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: d2f8a2f192dc319ad806aeef4bfbaeecc44b07a3
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
---
# <a name="readonly-c-reference"></a><span data-ttu-id="93e6d-102">readonly (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="93e6d-102">readonly (C# Reference)</span></span>
<span data-ttu-id="93e6d-103">La parola chiave `readonly` è un modificatore utilizzabile nei campi.</span><span class="sxs-lookup"><span data-stu-id="93e6d-103">The `readonly` keyword is a modifier that you can use on fields.</span></span> <span data-ttu-id="93e6d-104">Quando una dichiarazione di campo include un modificatore `readonly`, le assegnazioni ai campi introdotte dalla dichiarazione possono verificarsi solo come parte della dichiarazione o in un costruttore della stessa classe.</span><span class="sxs-lookup"><span data-stu-id="93e6d-104">When a field declaration includes a `readonly` modifier, assignments to the fields introduced by the declaration can only occur as part of the declaration or in a constructor in the same class.</span></span>  
  
## <a name="readonly-field-example"></a><span data-ttu-id="93e6d-105">Esempio di campo di sola lettura</span><span class="sxs-lookup"><span data-stu-id="93e6d-105">Readonly field example</span></span>  
 <span data-ttu-id="93e6d-106">In questo esempio, il valore del campo `year` non può essere modificato nel metodo `ChangeYear`, anche se gli viene assegnato un valore nel costruttore della classe:</span><span class="sxs-lookup"><span data-stu-id="93e6d-106">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 <span data-ttu-id="93e6d-107">È possibile assegnare un valore a un campo `readonly` solo nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="93e6d-107">You can assign a value to a `readonly` field only in the following contexts:</span></span>  
  
-   <span data-ttu-id="93e6d-108">Quando la variabile viene inizializzata nella dichiarazione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="93e6d-108">When the variable is initialized in the declaration, for example:</span></span>  
  
    ```csharp  
    public readonly int y = 5;  
    ```  
  
-   <span data-ttu-id="93e6d-109">Per un campo di istanza, nei costruttori di istanza della classe che contiene la dichiarazione del campo, o per un campo statico, nel costruttore statico della classe che contiene la dichiarazione del campo.</span><span class="sxs-lookup"><span data-stu-id="93e6d-109">For an instance field, in the instance constructors of the class that contains the field declaration, or for a static field, in the static constructor of the class that contains the field declaration.</span></span> <span data-ttu-id="93e6d-110">Questi sono anche gli unici contesti in cui è possibile passare un campo `readonly` come parametro [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) o [ref](../../../csharp/language-reference/keywords/ref.md).</span><span class="sxs-lookup"><span data-stu-id="93e6d-110">These are also the only contexts in which it is valid to pass a `readonly` field as an [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) or [ref](../../../csharp/language-reference/keywords/ref.md) parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93e6d-111">La parola chiave `readonly` è diversa dalla parola chiave [const](../../../csharp/language-reference/keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="93e6d-111">The `readonly` keyword is different from the [const](../../../csharp/language-reference/keywords/const.md) keyword.</span></span> <span data-ttu-id="93e6d-112">Un campo `const` può essere inizializzato solo nella dichiarazione del campo.</span><span class="sxs-lookup"><span data-stu-id="93e6d-112">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="93e6d-113">Un campo `readonly` può essere inizializzato nella dichiarazione o in un costruttore.</span><span class="sxs-lookup"><span data-stu-id="93e6d-113">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="93e6d-114">I campi `readonly` possono quindi presentare valori diversi a seconda del costruttore usato.</span><span class="sxs-lookup"><span data-stu-id="93e6d-114">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="93e6d-115">Inoltre, mentre un campo `const` rappresenta una costante in fase di compilazione, il campo `readonly` può essere usato per le costanti in fase di esecuzione, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="93e6d-115">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>  
  
```csharp  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="comparing-readonly-and-non-readonly-instance-fields"></a><span data-ttu-id="93e6d-116">Confronto tra i campi readonly e non readonly</span><span class="sxs-lookup"><span data-stu-id="93e6d-116">Comparing readonly and non-readonly instance fields</span></span>  
 [!code-csharp[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 <span data-ttu-id="93e6d-117">Nell'esempio precedente, se si usa un'istruzione simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="93e6d-117">In the preceding example, if you use a statement like this:</span></span>  
  
 `p2.y = 66;        // Error`  
  
 <span data-ttu-id="93e6d-118">si otterrà il messaggio di errore del compilatore:</span><span class="sxs-lookup"><span data-stu-id="93e6d-118">you will get the compiler error message:</span></span>  
  
 `The left-hand side of an assignment must be an l-value`  
  
 <span data-ttu-id="93e6d-119">ovvero lo stesso errore che si ottiene quando si tenta di assegnare un valore a una costante.</span><span class="sxs-lookup"><span data-stu-id="93e6d-119">which is the same error you get when you attempt to assign a value to a constant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="93e6d-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="93e6d-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="93e6d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93e6d-121">See Also</span></span>  
 [<span data-ttu-id="93e6d-122">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="93e6d-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="93e6d-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="93e6d-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="93e6d-124">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="93e6d-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="93e6d-125">Modificatori</span><span class="sxs-lookup"><span data-stu-id="93e6d-125">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="93e6d-126">const</span><span class="sxs-lookup"><span data-stu-id="93e6d-126">const</span></span>](../../../csharp/language-reference/keywords/const.md)  
 [<span data-ttu-id="93e6d-127">Campi</span><span class="sxs-lookup"><span data-stu-id="93e6d-127">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)
