---
title: Default (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 18126a0a5b6254da0b43e806b3de1f5b2127e6a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="default-visual-basic"></a><span data-ttu-id="10e55-102">Default (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10e55-102">Default (Visual Basic)</span></span>
<span data-ttu-id="10e55-103">Identifica una proprietà come proprietà predefinita della relativa classe, struttura o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="10e55-103">Identifies a property as the default property of its class, structure, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10e55-104">Note</span><span class="sxs-lookup"><span data-stu-id="10e55-104">Remarks</span></span>  
 <span data-ttu-id="10e55-105">È possibile designare una classe, struttura o interfaccia al massimo una delle relative proprietà come il *proprietà predefinita*, a condizione che accetti almeno un parametro.</span><span class="sxs-lookup"><span data-stu-id="10e55-105">A class, structure, or interface can designate at most one of its properties as the *default property*, provided that property takes at least one parameter.</span></span> <span data-ttu-id="10e55-106">Se il codice crea un riferimento a una classe o struttura senza specificare un membro, Visual Basic risolve il riferimento alla proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="10e55-106">If code makes a reference to a class or structure without specifying a member, Visual Basic resolves that reference to the default property.</span></span>  
  
 <span data-ttu-id="10e55-107">Proprietà predefinite può determinare un lieve riduzione del numero di caratteri del codice sorgente, ma può rendere più difficile la lettura di codice.</span><span class="sxs-lookup"><span data-stu-id="10e55-107">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="10e55-108">Se il codice chiamante non ha familiarità con la classe o struttura, quando fa riferimento al nome di classe o struttura non può essere determinato se il riferimento accede la classe o struttura o una proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="10e55-108">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="10e55-109">Questo può causare errori del compilatore o meno evidenti della logica di runtime.</span><span class="sxs-lookup"><span data-stu-id="10e55-109">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="10e55-110">Piuttosto, è possibile ridurre il rischio di errori di proprietà predefiniti utilizzando sempre la [istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) per impostare il tipo di compilatore controllo `On`.</span><span class="sxs-lookup"><span data-stu-id="10e55-110">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="10e55-111">Se si intende utilizzare una struttura o classe predefiniti nel codice, è necessario determinare se dispone di una proprietà predefinita e in tal caso, il relativo nome novità.</span><span class="sxs-lookup"><span data-stu-id="10e55-111">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="10e55-112">A causa di questi svantaggi, è consigliabile non definire proprietà predefinite.</span><span class="sxs-lookup"><span data-stu-id="10e55-112">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="10e55-113">Per la leggibilità del codice, è necessario anche valutare fare sempre riferimento a tutte le proprietà in modo esplicito, anche le proprietà predefinite.</span><span class="sxs-lookup"><span data-stu-id="10e55-113">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
 <span data-ttu-id="10e55-114">Il `Default` modificatore può essere utilizzato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="10e55-114">The `Default` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="10e55-115">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="10e55-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="10e55-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10e55-116">See Also</span></span>  
 [<span data-ttu-id="10e55-117">Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="10e55-117">How to: Declare and Call a Default Property in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="10e55-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="10e55-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
