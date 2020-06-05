---
title: Predefinito
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: 0c2808795d6fcbad7892369fd7f460ebf0406093
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372972"
---
# <a name="default-visual-basic"></a><span data-ttu-id="634f8-102">Default (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="634f8-102">Default (Visual Basic)</span></span>
<span data-ttu-id="634f8-103">Identifica una proprietà come proprietà predefinita della relativa classe, struttura o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="634f8-103">Identifies a property as the default property of its class, structure, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="634f8-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="634f8-104">Remarks</span></span>  
 <span data-ttu-id="634f8-105">Una classe, una struttura o un'interfaccia può definire al massimo una delle proprietà come *proprietà predefinita*, purché la proprietà accetti almeno un parametro.</span><span class="sxs-lookup"><span data-stu-id="634f8-105">A class, structure, or interface can designate at most one of its properties as the *default property*, provided that property takes at least one parameter.</span></span> <span data-ttu-id="634f8-106">Se il codice fa riferimento a una classe o a una struttura senza specificare un membro, Visual Basic risolve il riferimento alla proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="634f8-106">If code makes a reference to a class or structure without specifying a member, Visual Basic resolves that reference to the default property.</span></span>  
  
 <span data-ttu-id="634f8-107">Le proprietà predefinite possono causare una riduzione ridotta dei caratteri di codice sorgente, ma possono rendere il codice più difficile da leggere.</span><span class="sxs-lookup"><span data-stu-id="634f8-107">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="634f8-108">Se il codice chiamante non ha familiarità con la classe o la struttura, quando fa riferimento al nome della classe o della struttura, non può essere certo se il riferimento accede alla classe o alla struttura o a una proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="634f8-108">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="634f8-109">Questo può causare errori del compilatore o errori di logica di run-time sottili.</span><span class="sxs-lookup"><span data-stu-id="634f8-109">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="634f8-110">È possibile ridurre in qualche modo la probabilità di errori di proprietà predefiniti usando sempre l' [istruzione Option Strict](../statements/option-strict-statement.md) per impostare il controllo dei tipi del compilatore su `On` .</span><span class="sxs-lookup"><span data-stu-id="634f8-110">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="634f8-111">Se si prevede di usare una classe o una struttura predefinita nel codice, è necessario determinare se dispone di una proprietà predefinita e, in caso affermativo, il nome.</span><span class="sxs-lookup"><span data-stu-id="634f8-111">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="634f8-112">A causa di questi svantaggi, è consigliabile non definire le proprietà predefinite.</span><span class="sxs-lookup"><span data-stu-id="634f8-112">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="634f8-113">Per la leggibilità del codice, è consigliabile considerare sempre il riferimento a tutte le proprietà in modo esplicito, anche le proprietà predefinite.</span><span class="sxs-lookup"><span data-stu-id="634f8-113">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
 <span data-ttu-id="634f8-114">Il `Default` modificatore può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="634f8-114">The `Default` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="634f8-115">Property Statement</span><span class="sxs-lookup"><span data-stu-id="634f8-115">Property Statement</span></span>](../statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="634f8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="634f8-116">See also</span></span>

- [<span data-ttu-id="634f8-117">Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="634f8-117">How to: Declare and Call a Default Property in Visual Basic</span></span>](../../programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="634f8-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="634f8-118">Keywords</span></span>](../keywords/index.md)
