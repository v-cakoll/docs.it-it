---
title: 'Procedura: Creare una routine (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 56099d334a03e85b816cf48983cbbead0784ef5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665806"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="79648-102">Procedura: Creare una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79648-102">How to: Create a Procedure (Visual Basic)</span></span>
<span data-ttu-id="79648-103">Una routine racchiusa tra un'istruzione di dichiarazione iniziale (`Sub` oppure `Function`) e un'istruzione di dichiarazione finale (`End Sub` o `End Function`).</span><span class="sxs-lookup"><span data-stu-id="79648-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="79648-104">Tutto il codice della routine è compresa tra queste istruzioni.</span><span class="sxs-lookup"><span data-stu-id="79648-104">All the procedure's code lies between these statements.</span></span>  
  
 <span data-ttu-id="79648-105">Una routine non può contenere un'altra routine, in modo che le relative istruzioni iniziale e finale devono essere all'esterno di qualsiasi altra routine.</span><span class="sxs-lookup"><span data-stu-id="79648-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>  
  
 <span data-ttu-id="79648-106">Se si dispone di codice che esegue la stessa attività in posizioni diverse, è possibile scrivere attività una sola volta come una procedura e chiamarlo successivamente da diverse posizioni nel codice.</span><span class="sxs-lookup"><span data-stu-id="79648-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="79648-107">Per creare una routine che non restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="79648-107">To create a procedure that does not return a value</span></span>  
  
1. <span data-ttu-id="79648-108">Di fuori di qualsiasi altra routine, usare una `Sub` istruzione, seguito da un `End Sub` istruzione.</span><span class="sxs-lookup"><span data-stu-id="79648-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="79648-109">Nel `Sub` istruzione, seguire la `Sub` parola chiave con il nome della routine, quindi l'elenco di parametri tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="79648-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="79648-110">È possibile inserire istruzioni di codice della stored procedure tra il `Sub` e `End Sub` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="79648-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="79648-111">Per creare una stored procedure che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="79648-111">To create a procedure that returns a value</span></span>  
  
1. <span data-ttu-id="79648-112">Di fuori di qualsiasi altra routine, usare una `Function` istruzione, seguito da un `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="79648-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2. <span data-ttu-id="79648-113">Nel `Function` istruzione, seguire la `Function` parola chiave con il nome della routine, quindi l'elenco di parametri tra parentesi e quindi un `As` clausola che specifica il tipo di dati del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="79648-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>  
  
3. <span data-ttu-id="79648-114">È possibile inserire istruzioni di codice della stored procedure tra il `Function` e `End Function` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="79648-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
4. <span data-ttu-id="79648-115">Usare un `Return` istruzione per restituire il valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="79648-115">Use a `Return` statement to return the value to the calling code.</span></span>  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="79648-116">Per collegare la nuova routine con i blocchi di codice precedenti ricorrenti</span><span class="sxs-lookup"><span data-stu-id="79648-116">To connect your new procedure with the old, repetitive blocks of code</span></span>  
  
1. <span data-ttu-id="79648-117">Assicurarsi che si definisce la nuova routine in una posizione in cui il vecchio codice possa accedervi.</span><span class="sxs-lookup"><span data-stu-id="79648-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>  
  
2. <span data-ttu-id="79648-118">Nel blocco di codice precedente e ripetitive, sostituire le istruzioni che eseguono le attività ripetitive con una singola istruzione che chiama il `Sub` o `Function` procedure.</span><span class="sxs-lookup"><span data-stu-id="79648-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>  
  
3. <span data-ttu-id="79648-119">Se la routine è una `Function` che restituisce un valore, assicurarsi che l'istruzione chiama esegua un'azione con il valore restituito, ad esempio archiviare i dati in una variabile, in caso contrario il valore andranno perso.</span><span class="sxs-lookup"><span data-stu-id="79648-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79648-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="79648-120">Example</span></span>  
 <span data-ttu-id="79648-121">Nell'esempio `Function` procedure calcola il lato lungo, ovvero l'ipotenusa di un triangolo rettangolo, in base ai valori degli altri due lati.</span><span class="sxs-lookup"><span data-stu-id="79648-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="79648-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79648-122">See also</span></span>

- [<span data-ttu-id="79648-123">Routine</span><span class="sxs-lookup"><span data-stu-id="79648-123">Procedures</span></span>](./index.md)
- [<span data-ttu-id="79648-124">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="79648-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="79648-125">Routine Function</span><span class="sxs-lookup"><span data-stu-id="79648-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="79648-126">Routine Property</span><span class="sxs-lookup"><span data-stu-id="79648-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="79648-127">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="79648-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="79648-128">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="79648-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="79648-129">Routine ricorsive</span><span class="sxs-lookup"><span data-stu-id="79648-129">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="79648-130">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="79648-130">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="79648-131">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="79648-131">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="79648-132">Programmazione orientata a oggetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79648-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
