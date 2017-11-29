---
title: Altre strutture di controllo (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 09e59d25b3b2fc89026295e8500c30dad7b75086
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="def51-102">Altre strutture di controllo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="def51-102">Other Control Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="def51-103">fornisce le strutture di controllo che consentono di eliminare una risorsa o ridurre il numero di volte in cui che è necessario ripetere un riferimento all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="def51-103"> provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="def51-104">Utilizzo... Usando la costruzione di fine</span><span class="sxs-lookup"><span data-stu-id="def51-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="def51-105">Il `Using...End Using` costruzione definisce un blocco di istruzioni all'interno del quale utilizza di una risorsa, ad esempio una connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="def51-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="def51-106">Facoltativamente è possibile acquisire la risorsa con il `Using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="def51-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="def51-107">Quando si esce dal `Using` blocco [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Elimina automaticamente la risorsa in modo che sia disponibile per altro codice.</span><span class="sxs-lookup"><span data-stu-id="def51-107">When you exit the `Using` block, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="def51-108">La risorsa deve essere locale ed eliminabile.</span><span class="sxs-lookup"><span data-stu-id="def51-108">The resource must be local and disposable.</span></span> <span data-ttu-id="def51-109">Per altre informazioni, vedere [Istruzione using](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="def51-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="def51-110">Con... Termina con la costruzione</span><span class="sxs-lookup"><span data-stu-id="def51-110">With...End With Construction</span></span>  
 <span data-ttu-id="def51-111">Il `With...End With` costruzione consente di specificare un riferimento all'oggetto una volta e quindi eseguire una serie di istruzioni per accedere ai relativi membri.</span><span class="sxs-lookup"><span data-stu-id="def51-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="def51-112">Questo può semplificare il codice e migliorare le prestazioni poiché [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] non è necessario ristabilire il riferimento per ogni istruzione che vi accede.</span><span class="sxs-lookup"><span data-stu-id="def51-112">This can simplify your code and improve performance because [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="def51-113">Per ulteriori informazioni, vedere [con... Terminare con l'istruzione](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="def51-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="def51-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="def51-114">See Also</span></span>  
 [<span data-ttu-id="def51-115">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="def51-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="def51-116">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="def51-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="def51-117">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="def51-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="def51-118">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="def51-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="def51-119">Istruzione Using</span><span class="sxs-lookup"><span data-stu-id="def51-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)  
 [<span data-ttu-id="def51-120">Istruzione With...End With</span><span class="sxs-lookup"><span data-stu-id="def51-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
