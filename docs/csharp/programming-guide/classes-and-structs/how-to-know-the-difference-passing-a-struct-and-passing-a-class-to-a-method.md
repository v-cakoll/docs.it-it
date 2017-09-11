---
title: 'Procedura: differenza tra il passaggio a un metodo di uno struct e di un riferimento a una classe (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- structs [C#], passing as method parameter
- passing parameters [C#], structs vs. classes
- methods [C#], passing classes vs. structs
ms.assetid: 9c1313a6-32a8-4ea7-a59f-450f66af628b
caps.latest.revision: 25
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
ms.openlocfilehash: 1a4508c8765ac678fd371180cb0c3ece3e1d9a44
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-know-the-difference-between-passing-a-struct-and-passing-a-class-reference-to-a-method-c-programming-guide"></a><span data-ttu-id="be6c3-102">Procedura: differenza tra il passaggio a un metodo di uno struct e di un riferimento a una classe (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="be6c3-102">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method (C# Programming Guide)</span></span>
<span data-ttu-id="be6c3-103">L'esempio seguente mostra la differenza tra passare uno [struct](../../../csharp/language-reference/keywords/struct.md) a un metodo e passare un'istanza di una [classe](../../../csharp/language-reference/keywords/class.md) a un metodo.</span><span class="sxs-lookup"><span data-stu-id="be6c3-103">The following example demonstrates how passing a [struct](../../../csharp/language-reference/keywords/struct.md) to a method differs from passing a [class](../../../csharp/language-reference/keywords/class.md) instance to a method.</span></span> <span data-ttu-id="be6c3-104">Nell'esempio entrambi gli argomenti (struct e istanza di classe) vengono passati in base al valore ed entrambi i metodi modificano il valore di un campo dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="be6c3-104">In the example, both of the arguments (struct and class instance) are passed by value, and both methods change the value of one field of the argument.</span></span> <span data-ttu-id="be6c3-105">I risultati dei due metodi non sono tuttavia uguali perché ciò che viene passato quando si passa uno struct è diverso da ciò che viene passato quando si passa un'istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="be6c3-105">However, the results of the two methods are not the same because what is passed when you pass a struct differs from what is passed when you pass an instance of a class.</span></span>  
  
 <span data-ttu-id="be6c3-106">Poiché uno struct è un [tipo valore](../../../csharp/language-reference/keywords/value-types.md), quando si [passa uno struct in base al valore](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md) a un metodo, il metodo riceve una copia dell'argomento dello struct, su cui opera.</span><span class="sxs-lookup"><span data-stu-id="be6c3-106">Because a struct is a [value type](../../../csharp/language-reference/keywords/value-types.md), when you [pass a struct by value](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md) to a method, the method receives and operates on a copy of the struct argument.</span></span> <span data-ttu-id="be6c3-107">Il metodo non ha accesso allo struct originale nella chiamata e quindi non può modificarlo in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="be6c3-107">The method has no access to the original struct in the calling method and therefore can't change it in any way.</span></span> <span data-ttu-id="be6c3-108">Il metodo può modificare solo la copia.</span><span class="sxs-lookup"><span data-stu-id="be6c3-108">The method can change only the copy.</span></span>  
  
 <span data-ttu-id="be6c3-109">Un'istanza di classe è un [tipo riferimento](../../../csharp/language-reference/keywords/reference-types.md), non un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="be6c3-109">A class instance is a [reference type](../../../csharp/language-reference/keywords/reference-types.md), not a value type.</span></span> <span data-ttu-id="be6c3-110">Quando si [passa un tipo riferimento in base al valore](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) a un metodo, il metodo riceve una copia del riferimento all'istanza di classe.</span><span class="sxs-lookup"><span data-stu-id="be6c3-110">When [a reference type is passed by value](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) to a method, the method receives a copy of the reference to the class instance.</span></span> <span data-ttu-id="be6c3-111">Ciò significa che il metodo riceve una copia dell'indirizzo dell'istanza, non una copia dell'istanza stessa.</span><span class="sxs-lookup"><span data-stu-id="be6c3-111">That is, the method receives a copy of the address of the instance, not a copy of the instance itself.</span></span> <span data-ttu-id="be6c3-112">L'istanza di classe nel metodo chiamante ha un indirizzo, il parametro nel metodo chiamato ha una copia dell'indirizzo ed entrambi gli indirizzi fanno riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="be6c3-112">The class instance in the calling method has an address, the parameter in the called method has a copy of the address, and both addresses refer to the same object.</span></span> <span data-ttu-id="be6c3-113">Poiché il parametro contiene solo una copia dell'indirizzo, il metodo chiamato non può modificare l'indirizzo dell'istanza di classe nel metodo chiamante.</span><span class="sxs-lookup"><span data-stu-id="be6c3-113">Because the parameter contains only a copy of the address, the called method cannot change the address of the class instance in the calling method.</span></span> <span data-ttu-id="be6c3-114">Il metodo chiamato può tuttavia usare l'indirizzo per accedere ai membri della classe a cui fanno riferimento sia l'indirizzo originale che la copia.</span><span class="sxs-lookup"><span data-stu-id="be6c3-114">However, the called method can use the address to access the class members that both the original address and the copy reference.</span></span> <span data-ttu-id="be6c3-115">Se il metodo chiamato modifica un membro della classe, viene modificata anche l'istanza di classe originale nel metodo chiamante.</span><span class="sxs-lookup"><span data-stu-id="be6c3-115">If the called method changes a class member, the original class instance in the calling method also changes.</span></span>  
  
 <span data-ttu-id="be6c3-116">L'output dell'esempio seguente illustra la differenza.</span><span class="sxs-lookup"><span data-stu-id="be6c3-116">The output of the following example illustrates the difference.</span></span> <span data-ttu-id="be6c3-117">Il valore del campo `willIChange` dell'istanza di classe viene modificato dalla chiamata al metodo `ClassTaker` perché il metodo usa l'indirizzo nel parametro per trovare il campo specificato dell'istanza di classe.</span><span class="sxs-lookup"><span data-stu-id="be6c3-117">The value of the `willIChange` field of the class instance is changed by the call to method `ClassTaker` because the method uses the address in the parameter to find the specified field of the class instance.</span></span> <span data-ttu-id="be6c3-118">Il campo `willIChange` dello struct nel metodo chiamante non viene modificato dalla chiamata al metodo `StructTaker` perché il valore dell'argomento è una copia dello struct, non una copia del relativo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="be6c3-118">The `willIChange` field of the struct in the calling method is not changed by the call to method `StructTaker` because the value of the argument is a copy of the struct itself, not a copy of its address.</span></span> <span data-ttu-id="be6c3-119">`StructTaker` modifica la copia e la copia viene persa quando la chiamata a `StructTaker` viene completata.</span><span class="sxs-lookup"><span data-stu-id="be6c3-119">`StructTaker` changes the copy, and the copy is lost when the call to `StructTaker` is completed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be6c3-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="be6c3-120">Example</span></span>  
 <span data-ttu-id="be6c3-121">[!code-cs[csProgGuideObjects#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="be6c3-121">[!code-cs[csProgGuideObjects#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be6c3-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be6c3-122">See Also</span></span>  
 <span data-ttu-id="be6c3-123">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="be6c3-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="be6c3-124">[Classi](../../../csharp/programming-guide/classes-and-structs/classes.md) </span><span class="sxs-lookup"><span data-stu-id="be6c3-124">[Classes](../../../csharp/programming-guide/classes-and-structs/classes.md) </span></span>  
 <span data-ttu-id="be6c3-125">[Struct](../../../csharp/programming-guide/classes-and-structs/structs.md) </span><span class="sxs-lookup"><span data-stu-id="be6c3-125">[Structs](../../../csharp/programming-guide/classes-and-structs/structs.md) </span></span>  
 [<span data-ttu-id="be6c3-126">Passaggio di parametri</span><span class="sxs-lookup"><span data-stu-id="be6c3-126">Passing Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)

