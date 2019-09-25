---
title: 'Procedura: Creazione di una procedura (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 2cf4c788ec421c1e74ef7198496a92149e049752
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216727"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="4069d-102">Procedura: Creazione di una procedura (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4069d-102">How to: Create a Procedure (Visual Basic)</span></span>

<span data-ttu-id="4069d-103">È possibile racchiudere una procedura tra un'istruzione di Dichiarazione`Sub` iniziale `Function`(o) e un'istruzione di`End Sub` Dichiarazione `End Function`finale (o).</span><span class="sxs-lookup"><span data-stu-id="4069d-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="4069d-104">Tutto il codice della procedura si trova tra queste istruzioni.</span><span class="sxs-lookup"><span data-stu-id="4069d-104">All the procedure's code lies between these statements.</span></span>

 <span data-ttu-id="4069d-105">Una routine non può contenere un'altra procedura, quindi le istruzioni iniziali e finali devono essere esterne a qualsiasi altra procedura.</span><span class="sxs-lookup"><span data-stu-id="4069d-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>

 <span data-ttu-id="4069d-106">Se si dispone di codice che esegue la stessa attività in posizioni diverse, è possibile scrivere l'attività una sola volta come procedura e quindi chiamarla da posizioni diverse nel codice.</span><span class="sxs-lookup"><span data-stu-id="4069d-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="4069d-107">Per creare una routine che non restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="4069d-107">To create a procedure that does not return a value</span></span>

1. <span data-ttu-id="4069d-108">All'esterno di qualsiasi altra procedura, `Sub` utilizzare un'istruzione, seguita `End Sub` da un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="4069d-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>

2. <span data-ttu-id="4069d-109">Nell'istruzione seguire la `Sub` parola chiave con il nome della procedura, quindi l'elenco di parametri tra parentesi. `Sub`</span><span class="sxs-lookup"><span data-stu-id="4069d-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>

3. <span data-ttu-id="4069d-110">Inserire le istruzioni di codice della stored procedure `Sub` tra `End Sub` le istruzioni e.</span><span class="sxs-lookup"><span data-stu-id="4069d-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>

### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="4069d-111">Per creare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="4069d-111">To create a procedure that returns a value</span></span>

1. <span data-ttu-id="4069d-112">All'esterno di qualsiasi altra procedura, `Function` utilizzare un'istruzione, seguita `End Function` da un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="4069d-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>

2. <span data-ttu-id="4069d-113">Nell'istruzione seguire la `Function` parola chiave con il nome della procedura, quindi l'elenco di parametri tra parentesi e quindi una `As` clausola che specifica il tipo di dati del valore restituito. `Function`</span><span class="sxs-lookup"><span data-stu-id="4069d-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>

3. <span data-ttu-id="4069d-114">Inserire le istruzioni di codice della stored procedure `Function` tra `End Function` le istruzioni e.</span><span class="sxs-lookup"><span data-stu-id="4069d-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>

4. <span data-ttu-id="4069d-115">Utilizzare un' `Return` istruzione per restituire il valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="4069d-115">Use a `Return` statement to return the value to the calling code.</span></span>

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="4069d-116">Per connettere la nuova procedura con i blocchi di codice precedenti e ripetitivi</span><span class="sxs-lookup"><span data-stu-id="4069d-116">To connect your new procedure with the old, repetitive blocks of code</span></span>

1. <span data-ttu-id="4069d-117">Assicurarsi di definire la nuova procedura in una posizione in cui il codice precedente può accedervi.</span><span class="sxs-lookup"><span data-stu-id="4069d-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>

2. <span data-ttu-id="4069d-118">Nel blocco di codice precedente e ripetitivo sostituire le istruzioni che eseguono l'attività ripetitiva con una singola istruzione che chiama `Sub` la `Function` routine o.</span><span class="sxs-lookup"><span data-stu-id="4069d-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>

3. <span data-ttu-id="4069d-119">Se la routine è una `Function` che restituisce un valore, assicurarsi che l'istruzione chiamante esegua un'azione con il valore restituito, ad esempio archiviarla in una variabile, altrimenti il valore andrà perso.</span><span class="sxs-lookup"><span data-stu-id="4069d-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>

## <a name="example"></a><span data-ttu-id="4069d-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="4069d-120">Example</span></span>

 <span data-ttu-id="4069d-121">La procedura `Function` seguente calcola il lato più lungo, o ipotenusa, di un triangolo rettangolo, dati i valori per gli altri due lati:</span><span class="sxs-lookup"><span data-stu-id="4069d-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides:</span></span>

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="4069d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4069d-122">See also</span></span>

- [<span data-ttu-id="4069d-123">Routine</span><span class="sxs-lookup"><span data-stu-id="4069d-123">Procedures</span></span>](index.md)
- [<span data-ttu-id="4069d-124">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="4069d-124">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="4069d-125">Routine Function</span><span class="sxs-lookup"><span data-stu-id="4069d-125">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="4069d-126">Routine Property</span><span class="sxs-lookup"><span data-stu-id="4069d-126">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="4069d-127">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="4069d-127">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="4069d-128">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="4069d-128">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="4069d-129">Routine ricorsive</span><span class="sxs-lookup"><span data-stu-id="4069d-129">Recursive Procedures</span></span>](recursive-procedures.md)
- [<span data-ttu-id="4069d-130">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="4069d-130">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="4069d-131">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="4069d-131">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="4069d-132">Programmazione orientata a oggetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4069d-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
