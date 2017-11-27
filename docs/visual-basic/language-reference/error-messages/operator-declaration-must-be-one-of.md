---
title: 'Dichiarazione dell''operatore deve essere uno di: +,-, *,-, -, ^, &amp;, Like, Mod e, Or, Xor, non, &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;=, &gt; , &gt;=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords: BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80c8358dd13105c18e73e94735a51b02d5bd22c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a><span data-ttu-id="2ec15-102">Dichiarazione dell'operatore deve essere uno di: +,-, *,\,/, ^, &amp;, Like, Mod e, Or, Xor, non, &lt; &lt;, &gt; &gt;...</span><span class="sxs-lookup"><span data-stu-id="2ec15-102">Operator declaration must be one of:  +,-,*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;...</span></span>
<span data-ttu-id="2ec15-103">È possibile dichiarare solo gli operatori che sono idoneo per l'overload.</span><span class="sxs-lookup"><span data-stu-id="2ec15-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="2ec15-104">Nella tabella seguente elenca gli operatori che è possibile dichiarare.</span><span class="sxs-lookup"><span data-stu-id="2ec15-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="2ec15-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="2ec15-105">Type</span></span>|<span data-ttu-id="2ec15-106">Operatori</span><span class="sxs-lookup"><span data-stu-id="2ec15-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="2ec15-107">Unario</span><span class="sxs-lookup"><span data-stu-id="2ec15-107">Unary</span></span>|<span data-ttu-id="2ec15-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="2ec15-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="2ec15-109">Binario</span><span class="sxs-lookup"><span data-stu-id="2ec15-109">Binary</span></span>|<span data-ttu-id="2ec15-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="2ec15-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="2ec15-111">Conversione (unario)</span><span class="sxs-lookup"><span data-stu-id="2ec15-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="2ec15-112">Si noti che il `=` operatore nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="2ec15-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="2ec15-113">**ID errore:** BC33000</span><span class="sxs-lookup"><span data-stu-id="2ec15-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2ec15-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="2ec15-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="2ec15-115">Selezionare un operatore dal set di operatori che supportano l'overload.</span><span class="sxs-lookup"><span data-stu-id="2ec15-115">Select an operator from the set of overloadable operators.</span></span>  
  
2.  <span data-ttu-id="2ec15-116">Se è necessario eseguire l'overload di un operatore che non può essere sottoposto a overload direttamente, creare una routine `Function` che accetti i parametri appropriati e restituisca il valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="2ec15-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec15-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ec15-117">See Also</span></span>  
 [<span data-ttu-id="2ec15-118">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="2ec15-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="2ec15-119">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="2ec15-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="2ec15-120">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="2ec15-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="2ec15-121">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="2ec15-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="2ec15-122">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="2ec15-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
