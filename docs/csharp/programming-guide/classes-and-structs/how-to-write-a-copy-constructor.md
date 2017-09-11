---
title: 'Procedura: scrivere un costruttore di copia (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
caps.latest.revision: 20
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
ms.openlocfilehash: 712d9d5e792d025dd7c91d4c1809eeba96759757
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="2c39d-102">Procedura: scrivere un costruttore di copia (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="2c39d-102">How to: Write a Copy Constructor (C# Programming Guide)</span></span>
<span data-ttu-id="2c39d-103">C# non include un costruttore di copia per gli oggetti. È tuttavia possibile scriverne uno manualmente.</span><span class="sxs-lookup"><span data-stu-id="2c39d-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c39d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c39d-104">Example</span></span>  
 <span data-ttu-id="2c39d-105">Nell'esempio seguente, nella `Person`[classe](../../../csharp/language-reference/keywords/class.md) viene definito un costruttore di copia che accetta come argomento un'istanza di `Person`.</span><span class="sxs-lookup"><span data-stu-id="2c39d-105">In the following example, the `Person`[class](../../../csharp/language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="2c39d-106">I valori delle proprietà dell'argomento vengono assegnati alle proprietà della nuova istanza di `Person`.</span><span class="sxs-lookup"><span data-stu-id="2c39d-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="2c39d-107">Il codice contiene un costruttore di copia alternativo che invia le proprietà `Name` e `Age` dell'istanza che si vuole copiare nel costruttore di istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="2c39d-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 <span data-ttu-id="2c39d-108">[!code-cs[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2c39d-108">[!code-cs[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c39d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c39d-109">See Also</span></span>  
 <span data-ttu-id="2c39d-110"><xref:System.ICloneable></span><span class="sxs-lookup"><span data-stu-id="2c39d-110"><xref:System.ICloneable></span></span>   
 <span data-ttu-id="2c39d-111">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2c39d-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2c39d-112">[Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="2c39d-112">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="2c39d-113">[Costruttori](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="2c39d-113">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 [<span data-ttu-id="2c39d-114">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="2c39d-114">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

