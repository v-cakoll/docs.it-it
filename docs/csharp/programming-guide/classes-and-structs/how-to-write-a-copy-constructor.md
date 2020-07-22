---
title: Come scrivere un costruttore di copia-Guida per programmatori C#
description: Informazioni su come scrivere un costruttore di copia in C# che accetta un'istanza della classe e restituisce una nuova istanza con i valori dell'input.
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: beb2fcfaa36303eeaabd5278cf5e7a128282270e
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864228"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="cd4cb-103">Come scrivere un costruttore di copia (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="cd4cb-103">How to write a copy constructor (C# Programming Guide)</span></span>
<span data-ttu-id="cd4cb-104">C# non include un costruttore di copia per gli oggetti. È tuttavia possibile scriverne uno manualmente.</span><span class="sxs-lookup"><span data-stu-id="cd4cb-104">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd4cb-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd4cb-105">Example</span></span>  
 <span data-ttu-id="cd4cb-106">Nell'esempio seguente, nella `Person`[classe](../../language-reference/keywords/class.md) viene definito un costruttore di copia che accetta come argomento un'istanza di `Person`.</span><span class="sxs-lookup"><span data-stu-id="cd4cb-106">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="cd4cb-107">I valori delle proprietà dell'argomento vengono assegnati alle proprietà della nuova istanza di `Person`.</span><span class="sxs-lookup"><span data-stu-id="cd4cb-107">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="cd4cb-108">Il codice contiene un costruttore di copia alternativo che invia le proprietà `Name` e `Age` dell'istanza che si vuole copiare nel costruttore di istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="cd4cb-108">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="cd4cb-109">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="cd4cb-109">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="cd4cb-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="cd4cb-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cd4cb-111">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="cd4cb-111">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="cd4cb-112">Costruttori</span><span class="sxs-lookup"><span data-stu-id="cd4cb-112">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="cd4cb-113">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="cd4cb-113">Finalizers</span></span>](./destructors.md)
