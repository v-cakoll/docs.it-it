---
title: 'Procedura: creare una variabile che non cambia di valore (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1475553e64fef92ec3f3bb7e1b4fbfb357dbec8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="c11c7-102">Procedura: creare una variabile che non cambia di valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c11c7-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>
<span data-ttu-id="c11c7-103">Il concetto di una variabile che non cambia il relativo valore potrebbe sembrare contraddittorio.</span><span class="sxs-lookup"><span data-stu-id="c11c7-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="c11c7-104">Ma esistono situazioni in cui una costante non è fattibile ed è utile disporre di una variabile con un valore fisso.</span><span class="sxs-lookup"><span data-stu-id="c11c7-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="c11c7-105">In questo caso è possibile definire una variabile membro con il [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="c11c7-105">In such a case you can define a member variable with the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
 <span data-ttu-id="c11c7-106">Non è possibile utilizzare il [istruzione Const](../../../../visual-basic/language-reference/statements/const-statement.md) per dichiarare e assegnare un valore costante nelle circostanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="c11c7-106">You cannot use the [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>  
  
-   <span data-ttu-id="c11c7-107">Il `Const` istruzione non accetta il tipo di dati che si desidera utilizzare</span><span class="sxs-lookup"><span data-stu-id="c11c7-107">The `Const` statement does not accept the data type you want to use</span></span>  
  
-   <span data-ttu-id="c11c7-108">Non si conosce il valore in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="c11c7-108">You do not know the value at compile time</span></span>  
  
-   <span data-ttu-id="c11c7-109">Non è possibile calcolare il valore costante in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="c11c7-109">You are unable to compute the constant value at compile time</span></span>  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="c11c7-110">Per creare una variabile che non cambia di valore</span><span class="sxs-lookup"><span data-stu-id="c11c7-110">To create a variable that does not change in value</span></span>  
  
1.  <span data-ttu-id="c11c7-111">A livello di modulo, dichiarare una variabile membro con il [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md)e includere il [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="c11c7-111">At module level, declare a member variable with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     <span data-ttu-id="c11c7-112">È possibile specificare `ReadOnly` solo in una variabile membro.</span><span class="sxs-lookup"><span data-stu-id="c11c7-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="c11c7-113">Ciò significa che è necessario definire la variabile a livello di modulo, di fuori di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="c11c7-113">This means you must define the variable at module level, outside of any procedure.</span></span>  
  
2.  <span data-ttu-id="c11c7-114">Se è possibile calcolare il valore in un'unica istruzione in fase di compilazione, utilizzare una clausola di inizializzazione nel `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c11c7-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="c11c7-115">Seguire il [come](../../../../visual-basic/language-reference/statements/as-clause.md) clausola con un segno di uguale (`=`), seguito da un'espressione.</span><span class="sxs-lookup"><span data-stu-id="c11c7-115">Follow the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="c11c7-116">Assicurarsi che il compilatore può valutare questa espressione a un valore costante.</span><span class="sxs-lookup"><span data-stu-id="c11c7-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     <span data-ttu-id="c11c7-117">È possibile assegnare un valore per un `ReadOnly` variabile una sola volta.</span><span class="sxs-lookup"><span data-stu-id="c11c7-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="c11c7-118">Una volta eseguita questa operazione, nessun codice può essere modificata il relativo valore.</span><span class="sxs-lookup"><span data-stu-id="c11c7-118">Once you do so, no code can ever change its value.</span></span>  
  
     <span data-ttu-id="c11c7-119">Se si conosce il valore in fase di compilazione o non è possibile calcolare in fase di compilazione in un'unica istruzione, è possibile assegnarlo in fase di esecuzione in un costruttore.</span><span class="sxs-lookup"><span data-stu-id="c11c7-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="c11c7-120">A tale scopo, è necessario dichiarare il `ReadOnly` variabile a livello di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="c11c7-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="c11c7-121">Nel costruttore per quella classe o struttura, calcolare il valore della variabile fisso e assegnarlo alla variabile prima di restituire dal costruttore.</span><span class="sxs-lookup"><span data-stu-id="c11c7-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c11c7-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c11c7-122">See Also</span></span>  
 [<span data-ttu-id="c11c7-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="c11c7-123">WriteOnly</span></span>](../../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [<span data-ttu-id="c11c7-124">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="c11c7-124">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
