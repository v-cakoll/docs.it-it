---
title: 'Procedura: creare una routine'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: a831814c18f97991fca8067f1c9c8e491da1b665
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344905"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="fccaf-102">Procedura: creare una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fccaf-102">How to: Create a Procedure (Visual Basic)</span></span>

<span data-ttu-id="fccaf-103">È possibile racchiudere una procedura tra un'istruzione di dichiarazione iniziale (`Sub` o `Function`) e un'istruzione di dichiarazione finale (`End Sub` o `End Function`).</span><span class="sxs-lookup"><span data-stu-id="fccaf-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="fccaf-104">Tutto il codice della procedura si trova tra queste istruzioni.</span><span class="sxs-lookup"><span data-stu-id="fccaf-104">All the procedure's code lies between these statements.</span></span>

 <span data-ttu-id="fccaf-105">Una routine non può contenere un'altra procedura, quindi le istruzioni iniziali e finali devono essere esterne a qualsiasi altra procedura.</span><span class="sxs-lookup"><span data-stu-id="fccaf-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>

 <span data-ttu-id="fccaf-106">Se si dispone di codice che esegue la stessa attività in posizioni diverse, è possibile scrivere l'attività una sola volta come procedura e quindi chiamarla da posizioni diverse nel codice.</span><span class="sxs-lookup"><span data-stu-id="fccaf-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="fccaf-107">Per creare una routine che non restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="fccaf-107">To create a procedure that does not return a value</span></span>

1. <span data-ttu-id="fccaf-108">Al di fuori di qualsiasi altra procedura, utilizzare un'istruzione `Sub` seguita da un'istruzione `End Sub`.</span><span class="sxs-lookup"><span data-stu-id="fccaf-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>

2. <span data-ttu-id="fccaf-109">Nell'istruzione `Sub` seguire la parola chiave `Sub` con il nome della stored procedure, quindi l'elenco di parametri tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="fccaf-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>

3. <span data-ttu-id="fccaf-110">Inserire le istruzioni di codice della stored procedure tra le istruzioni `Sub` e `End Sub`.</span><span class="sxs-lookup"><span data-stu-id="fccaf-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>

### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="fccaf-111">Per creare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="fccaf-111">To create a procedure that returns a value</span></span>

1. <span data-ttu-id="fccaf-112">Al di fuori di qualsiasi altra procedura, utilizzare un'istruzione `Function` seguita da un'istruzione `End Function`.</span><span class="sxs-lookup"><span data-stu-id="fccaf-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>

2. <span data-ttu-id="fccaf-113">Nell'istruzione `Function` seguire la parola chiave `Function` con il nome della procedura, quindi l'elenco di parametri tra parentesi e quindi una clausola `As` che specifica il tipo di dati del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="fccaf-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>

3. <span data-ttu-id="fccaf-114">Inserire le istruzioni di codice della stored procedure tra le istruzioni `Function` e `End Function`.</span><span class="sxs-lookup"><span data-stu-id="fccaf-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>

4. <span data-ttu-id="fccaf-115">Utilizzare un'istruzione `Return` per restituire il valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="fccaf-115">Use a `Return` statement to return the value to the calling code.</span></span>

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="fccaf-116">Per connettere la nuova procedura con i blocchi di codice precedenti e ripetitivi</span><span class="sxs-lookup"><span data-stu-id="fccaf-116">To connect your new procedure with the old, repetitive blocks of code</span></span>

1. <span data-ttu-id="fccaf-117">Assicurarsi di definire la nuova procedura in una posizione in cui il codice precedente può accedervi.</span><span class="sxs-lookup"><span data-stu-id="fccaf-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>

2. <span data-ttu-id="fccaf-118">Nel blocco di codice precedente e ripetitivo sostituire le istruzioni che eseguono l'attività ripetitiva con una singola istruzione che chiama la routine `Sub` o `Function`.</span><span class="sxs-lookup"><span data-stu-id="fccaf-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>

3. <span data-ttu-id="fccaf-119">Se la routine è un `Function` che restituisce un valore, assicurarsi che l'istruzione chiamante esegua un'azione con il valore restituito, ad esempio archiviarla in una variabile, altrimenti il valore andrà perso.</span><span class="sxs-lookup"><span data-stu-id="fccaf-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>

## <a name="example"></a><span data-ttu-id="fccaf-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="fccaf-120">Example</span></span>

 <span data-ttu-id="fccaf-121">La seguente procedura `Function` calcola il lato più lungo, o ipotenusa, di un triangolo rettangolo, dati i valori per gli altri due lati:</span><span class="sxs-lookup"><span data-stu-id="fccaf-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides:</span></span>

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="fccaf-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fccaf-122">See also</span></span>

- [<span data-ttu-id="fccaf-123">Routine</span><span class="sxs-lookup"><span data-stu-id="fccaf-123">Procedures</span></span>](index.md)
- [<span data-ttu-id="fccaf-124">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="fccaf-124">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="fccaf-125">Routine Function</span><span class="sxs-lookup"><span data-stu-id="fccaf-125">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="fccaf-126">Routine Property</span><span class="sxs-lookup"><span data-stu-id="fccaf-126">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="fccaf-127">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="fccaf-127">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="fccaf-128">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="fccaf-128">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="fccaf-129">Routine ricorsive</span><span class="sxs-lookup"><span data-stu-id="fccaf-129">Recursive Procedures</span></span>](recursive-procedures.md)
- [<span data-ttu-id="fccaf-130">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="fccaf-130">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="fccaf-131">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="fccaf-131">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="fccaf-132">Programmazione orientata a oggetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fccaf-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
