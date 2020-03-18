---
title: Come scrivere un costruttore di copia - Guida per programmatori C
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: aa6feb1b07f491a90a78684e254910d387b9bccd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714849"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="c0b28-102">Come scrivere un costruttore di copia (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="c0b28-102">How to write a copy constructor (C# Programming Guide)</span></span>
<span data-ttu-id="c0b28-103">C# non include un costruttore di copia per gli oggetti. È tuttavia possibile scriverne uno manualmente.</span><span class="sxs-lookup"><span data-stu-id="c0b28-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0b28-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c0b28-104">Example</span></span>  
 <span data-ttu-id="c0b28-105">Nell'esempio seguente, nella `Person`[classe](../../language-reference/keywords/class.md) viene definito un costruttore di copia che accetta come argomento un'istanza di `Person`.</span><span class="sxs-lookup"><span data-stu-id="c0b28-105">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="c0b28-106">I valori delle proprietà dell'argomento vengono assegnati alle proprietà della nuova istanza di `Person`.</span><span class="sxs-lookup"><span data-stu-id="c0b28-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="c0b28-107">Il codice contiene un costruttore di copia alternativo che invia le proprietà `Name` e `Age` dell'istanza che si vuole copiare nel costruttore di istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="c0b28-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="c0b28-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0b28-108">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="c0b28-109">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c0b28-109">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c0b28-110">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="c0b28-110">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="c0b28-111">Costruttori</span><span class="sxs-lookup"><span data-stu-id="c0b28-111">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="c0b28-112">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="c0b28-112">Finalizers</span></span>](./destructors.md)
