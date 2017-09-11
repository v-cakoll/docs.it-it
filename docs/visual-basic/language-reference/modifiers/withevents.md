---
title: WithEvents (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.WithEvents
- WithEvents
dev_langs:
- VB
helpviewer_keywords:
- WithEvents keyword
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b956f8f0d6f0a2fd9f41c5df6d6c82b43fa09018
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="withevents-visual-basic"></a><span data-ttu-id="533e9-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="533e9-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="533e9-103">Specifica che una o più variabili membro dichiarato fare riferimento a un'istanza di una classe che può generare eventi.</span><span class="sxs-lookup"><span data-stu-id="533e9-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="533e9-104">Note</span><span class="sxs-lookup"><span data-stu-id="533e9-104">Remarks</span></span>  
 <span data-ttu-id="533e9-105">Quando una variabile viene definita mediante `WithEvents`, è possibile specificare in modo dichiarativo che un metodo gestisce gli eventi della variabile usando il `Handles` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="533e9-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="533e9-106">È possibile utilizzare `WithEvents` solo a livello di classe o modulo.</span><span class="sxs-lookup"><span data-stu-id="533e9-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="533e9-107">Ciò significa che il contesto della dichiarazione per un `WithEvents` variabile deve essere una classe o modulo e non può essere un file di origine, lo spazio dei nomi, struttura o routine.</span><span class="sxs-lookup"><span data-stu-id="533e9-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="533e9-108">Non è possibile utilizzare `WithEvents` su un membro della struttura.</span><span class="sxs-lookup"><span data-stu-id="533e9-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="533e9-109">È possibile dichiarare solo variabili singole, ovvero non matrici, con `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="533e9-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="533e9-110">Regole</span><span class="sxs-lookup"><span data-stu-id="533e9-110">Rules</span></span>  
  
-   <span data-ttu-id="533e9-111">**Tipi di elemento.**</span><span class="sxs-lookup"><span data-stu-id="533e9-111">**Element Types.**</span></span> <span data-ttu-id="533e9-112">È necessario dichiarare `WithEvents` le variabili come variabili oggetto in modo che accettino le istanze di classe.</span><span class="sxs-lookup"><span data-stu-id="533e9-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="533e9-113">Tuttavia, è possibile dichiarare le variabili come `Object`.</span><span class="sxs-lookup"><span data-stu-id="533e9-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="533e9-114">È necessario dichiararle come la classe specifica in grado di generare eventi.</span><span class="sxs-lookup"><span data-stu-id="533e9-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="533e9-115">Il `WithEvents` modificatore può essere utilizzato in questo contesto: [Dim (istruzione)](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="533e9-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="533e9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="533e9-116">See Also</span></span>  
 <span data-ttu-id="533e9-117">[Handle](../../../visual-basic/language-reference/statements/handles-clause.md) </span><span class="sxs-lookup"><span data-stu-id="533e9-117">[Handles](../../../visual-basic/language-reference/statements/handles-clause.md) </span></span>  
<span data-ttu-id="533e9-118"> [Parole chiave](../../../visual-basic/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="533e9-118"> [Keywords](../../../visual-basic/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="533e9-119"> [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="533e9-119"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
