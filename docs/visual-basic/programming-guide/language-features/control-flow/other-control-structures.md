---
title: Altre strutture di controllo (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
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
ms.openlocfilehash: 8f8bd57f193be0d7f410f7325355ffc47ab10e3f
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="df2aa-102">Altre strutture di controllo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df2aa-102">Other Control Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="df2aa-103">fornisce le strutture di controllo che consentono di eliminare una risorsa o ridurre il numero di volte in cui che è necessario ripetere un riferimento all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="df2aa-103"> provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="df2aa-104">Utilizzo... Usando la costruzione di fine</span><span class="sxs-lookup"><span data-stu-id="df2aa-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="df2aa-105">Il `Using...End Using` costruzione definisce un blocco di istruzioni all'interno del quale utilizza una risorsa, ad esempio una connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="df2aa-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="df2aa-106">Facoltativamente è possibile acquisire la risorsa con il `Using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="df2aa-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="df2aa-107">Quando si esce dal `Using` blocco [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Elimina automaticamente la risorsa in modo che sia disponibile per altro codice.</span><span class="sxs-lookup"><span data-stu-id="df2aa-107">When you exit the `Using` block, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="df2aa-108">La risorsa deve essere locale ed eliminabile.</span><span class="sxs-lookup"><span data-stu-id="df2aa-108">The resource must be local and disposable.</span></span> <span data-ttu-id="df2aa-109">Per ulteriori informazioni, vedere [istruzione Using](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="df2aa-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="df2aa-110">Con... Termina con la costruzione</span><span class="sxs-lookup"><span data-stu-id="df2aa-110">With...End With Construction</span></span>  
 <span data-ttu-id="df2aa-111">Il `With...End With` costruzione consente di specificare un riferimento all'oggetto una sola volta e quindi eseguire una serie di istruzioni che accedono ai membri.</span><span class="sxs-lookup"><span data-stu-id="df2aa-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="df2aa-112">Ciò consente di semplificare il codice e migliorare le prestazioni perché [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] non è necessario ristabilire il riferimento per ogni istruzione che vi accede.</span><span class="sxs-lookup"><span data-stu-id="df2aa-112">This can simplify your code and improve performance because [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="df2aa-113">Per ulteriori informazioni, vedere [con... Terminare con l'istruzione](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="df2aa-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df2aa-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df2aa-114">See Also</span></span>  
 <span data-ttu-id="df2aa-115">[Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="df2aa-115">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="df2aa-116"> [Strutture decisionali](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span><span class="sxs-lookup"><span data-stu-id="df2aa-116"> [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span></span>  
<span data-ttu-id="df2aa-117"> [Cicli (strutture)](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="df2aa-117"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="df2aa-118"> [Strutture di controllo annidate](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="df2aa-118"> [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span></span>  
<span data-ttu-id="df2aa-119"> [Istruzione using](../../../../visual-basic/language-reference/statements/using-statement.md) </span><span class="sxs-lookup"><span data-stu-id="df2aa-119"> [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md) </span></span>  
<span data-ttu-id="df2aa-120"> [Istruzione With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span><span class="sxs-lookup"><span data-stu-id="df2aa-120"> [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span></span>
