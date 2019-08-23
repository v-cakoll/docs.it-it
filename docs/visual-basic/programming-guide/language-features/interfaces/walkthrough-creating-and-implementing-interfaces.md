---
title: Creazione e implementazione di interfacce (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 62e301e9eb366d14b58088d3e2cda3b567d17f5b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923316"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="aefbf-102">Procedura dettagliata: Creazione e implementazione di interfacce (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aefbf-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>

<span data-ttu-id="aefbf-103">Le interfacce descrivono le caratteristiche di proprietà, metodi ed eventi, ma lasciano i dettagli di implementazione fino a strutture o classi.</span><span class="sxs-lookup"><span data-stu-id="aefbf-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="aefbf-104">In questa procedura dettagliata viene illustrato come dichiarare e implementare un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="aefbf-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aefbf-105">Questa procedura dettagliata non fornisce informazioni su come creare un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="aefbf-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a><span data-ttu-id="aefbf-106">Per definire un'interfaccia</span><span class="sxs-lookup"><span data-stu-id="aefbf-106">To define an interface</span></span>
  
1. <span data-ttu-id="aefbf-107">Aprire un nuovo progetto Applicazione Windows in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="aefbf-107">Open a new Visual Basic Windows Application project.</span></span>  
  
2. <span data-ttu-id="aefbf-108">Per aggiungere un nuovo modulo al progetto, fare clic su **Aggiungi modulo** nel menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="aefbf-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3. <span data-ttu-id="aefbf-109">Assegnare un nome al `Module1.vb` nuovo modulo e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="aefbf-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="aefbf-110">Viene visualizzato il codice per il nuovo modulo.</span><span class="sxs-lookup"><span data-stu-id="aefbf-110">The code for the new module is displayed.</span></span>  
  
4. <span data-ttu-id="aefbf-111">Definire un'interfaccia denominata `TestInterface` all' `Module1` interno di `Interface TestInterface` digitando `End Module` tra le `Module` istruzioni e e quindi premendo INVIO.</span><span class="sxs-lookup"><span data-stu-id="aefbf-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="aefbf-112">Nell' **editor di codice** viene rientrato il valore `End Interface` della `Interface` parola chiave e viene aggiunta un'istruzione per formare un blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="aefbf-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5. <span data-ttu-id="aefbf-113">Definire una proprietà, un metodo e un evento per l'interfaccia inserendo il codice seguente tra le `Interface` istruzioni `End Interface` e:</span><span class="sxs-lookup"><span data-stu-id="aefbf-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a><span data-ttu-id="aefbf-114">Implementazione</span><span class="sxs-lookup"><span data-stu-id="aefbf-114">Implementation</span></span>

 <span data-ttu-id="aefbf-115">È possibile notare che la sintassi utilizzata per dichiarare i membri di interfaccia è diversa dalla sintassi utilizzata per dichiarare i membri della classe.</span><span class="sxs-lookup"><span data-stu-id="aefbf-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="aefbf-116">Questa differenza riflette il fatto che le interfacce non possono contenere codice di implementazione.</span><span class="sxs-lookup"><span data-stu-id="aefbf-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
### <a name="to-implement-the-interface"></a><span data-ttu-id="aefbf-117">Per implementare l'interfaccia</span><span class="sxs-lookup"><span data-stu-id="aefbf-117">To implement the interface</span></span>
  
1. <span data-ttu-id="aefbf-118">Aggiungere una classe denominata `ImplementationClass` aggiungendo l'istruzione seguente a `Module1`, dopo l' `End Interface` istruzione, ma prima dell' `End Module` istruzione, quindi premendo INVIO:</span><span class="sxs-lookup"><span data-stu-id="aefbf-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     <span data-ttu-id="aefbf-119">Se si lavora all'interno dell'Integrated Development Environment, l' **editor di codice** fornisce un' `End Class` istruzione corrispondente quando si preme INVIO.</span><span class="sxs-lookup"><span data-stu-id="aefbf-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2. <span data-ttu-id="aefbf-120">Aggiungere l'istruzione `Implements` seguente a `ImplementationClass`, che denomina l'interfaccia implementata dalla classe:</span><span class="sxs-lookup"><span data-stu-id="aefbf-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     <span data-ttu-id="aefbf-121">Se elencato separatamente da altri elementi all'inizio di una classe o di una struttura, `Implements` l'istruzione indica che la classe o la struttura implementa un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="aefbf-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="aefbf-122">Se si lavora all'interno dell'Integrated Development Environment, l' **editor di codice** implementa i membri della classe `TestInterface` richiesti da quando si preme INVIO ed è possibile ignorare il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="aefbf-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3. <span data-ttu-id="aefbf-123">Se non si lavora all'interno del Integrated Development Environment, è necessario implementare tutti i membri dell'interfaccia `MyInterface`.</span><span class="sxs-lookup"><span data-stu-id="aefbf-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="aefbf-124">Aggiungere il codice seguente a `ImplementationClass` per implementare `Event1`, `Method1`e `Prop1`:</span><span class="sxs-lookup"><span data-stu-id="aefbf-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     <span data-ttu-id="aefbf-125">L' `Implements` istruzione denomina l'interfaccia e il membro di interfaccia in fase di implementazione.</span><span class="sxs-lookup"><span data-stu-id="aefbf-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4. <span data-ttu-id="aefbf-126">Completare la definizione di `Prop1` aggiungendo un campo privato alla classe in cui è archiviato il valore della proprietà:</span><span class="sxs-lookup"><span data-stu-id="aefbf-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     <span data-ttu-id="aefbf-127">Restituisce il valore di `pval` dalla funzione di accesso get della proprietà.</span><span class="sxs-lookup"><span data-stu-id="aefbf-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     <span data-ttu-id="aefbf-128">Impostare il valore di `pval` nella funzione di accesso set di proprietà.</span><span class="sxs-lookup"><span data-stu-id="aefbf-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. <span data-ttu-id="aefbf-129">Completare la definizione di `Method1` aggiungendo il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="aefbf-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="aefbf-130">Per testare l'implementazione dell'interfaccia</span><span class="sxs-lookup"><span data-stu-id="aefbf-130">To test the implementation of the interface</span></span>
  
1. <span data-ttu-id="aefbf-131">Fare clic con il pulsante destro del mouse sul modulo di avvio del progetto nella **Esplora soluzioni**, quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="aefbf-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="aefbf-132">Nell'editor viene visualizzata la classe per il form di avvio.</span><span class="sxs-lookup"><span data-stu-id="aefbf-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="aefbf-133">Per impostazione predefinita, viene chiamato `Form1`il form di avvio.</span><span class="sxs-lookup"><span data-stu-id="aefbf-133">By default, the startup form is called `Form1`.</span></span>  
  
2. <span data-ttu-id="aefbf-134">Aggiungere il campo `testInstance` seguente `Form1` alla classe:</span><span class="sxs-lookup"><span data-stu-id="aefbf-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     <span data-ttu-id="aefbf-135">Dichiarando `testInstance` come `WithEvents`, la `Form1` classe è in grado di gestire gli eventi.</span><span class="sxs-lookup"><span data-stu-id="aefbf-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3. <span data-ttu-id="aefbf-136">Aggiungere il gestore eventi seguente alla `Form1` classe per gestire gli eventi generati da: `testInstance`</span><span class="sxs-lookup"><span data-stu-id="aefbf-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. <span data-ttu-id="aefbf-137">Aggiungere una subroutine denominata `Test` `Form1` alla classe per testare la classe di implementazione:</span><span class="sxs-lookup"><span data-stu-id="aefbf-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     <span data-ttu-id="aefbf-138">La `Test` stored procedure crea un'istanza della classe che implementa `MyInterface`, assegna tale istanza al `testInstance` campo, imposta una proprietà ed esegue un metodo tramite l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="aefbf-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5. <span data-ttu-id="aefbf-139">Aggiungere il codice per chiamare `Test` la procedura `Form1 Load` dalla procedura del form di avvio:</span><span class="sxs-lookup"><span data-stu-id="aefbf-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. <span data-ttu-id="aefbf-140">Eseguire la `Test` procedura premendo F5.</span><span class="sxs-lookup"><span data-stu-id="aefbf-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="aefbf-141">Viene visualizzato il messaggio "Prop1 è stato impostato su 9".</span><span class="sxs-lookup"><span data-stu-id="aefbf-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="aefbf-142">Dopo aver fatto clic su OK, viene visualizzato il messaggio "il parametro X per Method1 è 5".</span><span class="sxs-lookup"><span data-stu-id="aefbf-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="aefbf-143">Fare clic su OK e viene visualizzato il messaggio "il gestore eventi ha rilevato l'evento".</span><span class="sxs-lookup"><span data-stu-id="aefbf-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aefbf-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aefbf-144">See also</span></span>

- [<span data-ttu-id="aefbf-145">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="aefbf-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="aefbf-146">Interfacce</span><span class="sxs-lookup"><span data-stu-id="aefbf-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="aefbf-147">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="aefbf-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="aefbf-148">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="aefbf-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)
