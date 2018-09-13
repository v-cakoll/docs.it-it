---
title: 'Procedura: scrivere un costruttore di copia (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: d6ecfc3659dcf533db0f4e7b67fdffd620a584fd
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271611"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="6af6b-102">Procedura: scrivere un costruttore di copia (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="6af6b-102">How to: Write a Copy Constructor (C# Programming Guide)</span></span>
<span data-ttu-id="6af6b-103">C# non include un costruttore di copia per gli oggetti. È tuttavia possibile scriverne uno manualmente.</span><span class="sxs-lookup"><span data-stu-id="6af6b-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6af6b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6af6b-104">Example</span></span>  
 <span data-ttu-id="6af6b-105">Nell'esempio seguente, nella `Person`[classe](../../../csharp/language-reference/keywords/class.md) viene definito un costruttore di copia che accetta come argomento un'istanza di `Person`.</span><span class="sxs-lookup"><span data-stu-id="6af6b-105">In the following example, the `Person`[class](../../../csharp/language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="6af6b-106">I valori delle proprietà dell'argomento vengono assegnati alle proprietà della nuova istanza di `Person`.</span><span class="sxs-lookup"><span data-stu-id="6af6b-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="6af6b-107">Il codice contiene un costruttore di copia alternativo che invia le proprietà `Name` e `Age` dell'istanza che si vuole copiare nel costruttore di istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="6af6b-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6af6b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6af6b-108">See Also</span></span>

- <xref:System.ICloneable>  
- [<span data-ttu-id="6af6b-109">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="6af6b-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6af6b-110">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="6af6b-110">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="6af6b-111">Costruttori</span><span class="sxs-lookup"><span data-stu-id="6af6b-111">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [<span data-ttu-id="6af6b-112">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="6af6b-112">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
