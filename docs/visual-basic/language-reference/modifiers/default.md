---
title: Default (Visual Basic)
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
ms.openlocfilehash: f78ffe42a9d618d44da2a50c0de831396576430c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836727"
---
# <a name="default-visual-basic"></a><span data-ttu-id="05d98-102">Default (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05d98-102">Default (Visual Basic)</span></span>
<span data-ttu-id="05d98-103">Identifica una proprietà come proprietà predefinita della relativa classe, struttura o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="05d98-103">Identifies a property as the default property of its class, structure, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05d98-104">Note</span><span class="sxs-lookup"><span data-stu-id="05d98-104">Remarks</span></span>  
 <span data-ttu-id="05d98-105">È possibile designare una classe, struttura o interfaccia al massimo una delle relative proprietà come il *predefiniti delle proprietà*, purché tali proprietà richiede almeno un parametro.</span><span class="sxs-lookup"><span data-stu-id="05d98-105">A class, structure, or interface can designate at most one of its properties as the *default property*, provided that property takes at least one parameter.</span></span> <span data-ttu-id="05d98-106">Se il codice crea un riferimento a una classe o struttura senza specificare un membro, Visual Basic risolve tale riferimento alla proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="05d98-106">If code makes a reference to a class or structure without specifying a member, Visual Basic resolves that reference to the default property.</span></span>  
  
 <span data-ttu-id="05d98-107">Proprietà predefinite può determinare un lieve riduzione del numero di caratteri del codice sorgente, ma è possibile rendere il codice più difficile da leggere.</span><span class="sxs-lookup"><span data-stu-id="05d98-107">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="05d98-108">Se il codice chiamante non abbia familiarità con la classe o struttura, quando effettua un riferimento al nome della classe o struttura non può essere determinato se il riferimento accede la classe o struttura stessa o una proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="05d98-108">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="05d98-109">Questo può causare errori del compilatore o meno evidenti in fase di esecuzione della logica.</span><span class="sxs-lookup"><span data-stu-id="05d98-109">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="05d98-110">In qualche modo, è possibile ridurre le probabilità di errori di proprietà predefiniti utilizzando sempre la [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) per impostare il tipo del compilatore controllo `On`.</span><span class="sxs-lookup"><span data-stu-id="05d98-110">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="05d98-111">Se si prevede di usare una struttura o classe predefinite nel codice, è necessario determinare se dispone di una proprietà predefinita e in tal caso, quali il nome sarà.</span><span class="sxs-lookup"><span data-stu-id="05d98-111">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="05d98-112">A causa di questi svantaggi, è necessario considerare che non definisce le proprietà predefinite.</span><span class="sxs-lookup"><span data-stu-id="05d98-112">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="05d98-113">Per la leggibilità del codice, è necessario considerare anche fare sempre riferimento a tutte le proprietà in modo esplicito, anche le proprietà predefinite.</span><span class="sxs-lookup"><span data-stu-id="05d98-113">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
 <span data-ttu-id="05d98-114">Il `Default` modificatore può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="05d98-114">The `Default` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="05d98-115">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="05d98-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="05d98-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05d98-116">See also</span></span>

- [<span data-ttu-id="05d98-117">Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="05d98-117">How to: Declare and Call a Default Property in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="05d98-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05d98-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
