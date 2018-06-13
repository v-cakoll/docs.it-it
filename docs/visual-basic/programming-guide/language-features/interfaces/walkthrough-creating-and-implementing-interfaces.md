---
title: Creazione e implementazione di interfacce (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: af9305deb60637b642d091501e743f2c7a57ccad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653611"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="8e7e6-102">Procedura dettagliata: creazione e implementazione di interfacce (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e7e6-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>

<span data-ttu-id="8e7e6-103">Interfacce descrivono le caratteristiche di proprietà, metodi ed eventi, ma i dettagli relativi all'implementazione fino a strutture o classi.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="8e7e6-104">Questa procedura dettagliata viene illustrato come dichiarare e implementare un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e7e6-105">Questa procedura dettagliata non fornisce informazioni su come creare un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a><span data-ttu-id="8e7e6-106">Per definire un'interfaccia</span><span class="sxs-lookup"><span data-stu-id="8e7e6-106">To define an interface</span></span>
  
1.  <span data-ttu-id="8e7e6-107">Aprire un nuovo progetto Applicazione Windows in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-107">Open a new Visual Basic Windows Application project.</span></span>  
  
2.  <span data-ttu-id="8e7e6-108">Aggiungere un nuovo modulo al progetto, fare clic su **Aggiungi modulo** sul **progetto** menu.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="8e7e6-109">Nome del nuovo modulo `Module1.vb` e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="8e7e6-110">Viene visualizzato il codice per il nuovo modulo.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-110">The code for the new module is displayed.</span></span>  
  
4.  <span data-ttu-id="8e7e6-111">Definire un'interfaccia denominata `TestInterface` all'interno di `Module1` digitando `Interface TestInterface` tra il `Module` e `End Module` istruzioni e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="8e7e6-112">Il **Editor di codice** rientri di `Interface` (parola chiave) e aggiunge un `End Interface` istruzione in modo da formare un blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5.  <span data-ttu-id="8e7e6-113">Definire un proprietà, metodi ed eventi per l'interfaccia inserendo il codice seguente tra i `Interface` e `End Interface` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="8e7e6-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a><span data-ttu-id="8e7e6-114">Implementazione</span><span class="sxs-lookup"><span data-stu-id="8e7e6-114">Implementation</span></span>

 <span data-ttu-id="8e7e6-115">È possibile notare che la sintassi utilizzata per dichiarare i membri di interfaccia è diversa da quella utilizzata per dichiarare i membri di classe.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="8e7e6-116">Questa differenza è dovuto al fatto che le interfacce non possono contenere codice di implementazione.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
### <a name="to-implement-the-interface"></a><span data-ttu-id="8e7e6-117">Per implementare l'interfaccia</span><span class="sxs-lookup"><span data-stu-id="8e7e6-117">To implement the interface</span></span>
  
1.  <span data-ttu-id="8e7e6-118">Aggiungere una classe denominata `ImplementationClass` aggiungendo l'istruzione seguente alle `Module1`, dopo il `End Interface` istruzione ma prima che il `End Module` istruzione e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="8e7e6-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     <span data-ttu-id="8e7e6-119">Se si lavora all'interno dell'ambiente di sviluppo integrato, il **Editor di codice** fornisce un corrispondente `End Class` istruzione quando si preme INVIO.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2.  <span data-ttu-id="8e7e6-120">Aggiungere il seguente `Implements` istruzione `ImplementationClass`, quali nome dell'interfaccia implementata dalla classe:</span><span class="sxs-lookup"><span data-stu-id="8e7e6-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     <span data-ttu-id="8e7e6-121">Quando elencata separatamente da altri elementi nella parte superiore di una classe o struttura, il `Implements` istruzione indica che la classe o struttura implementa un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="8e7e6-122">Se si lavora all'interno dell'ambiente di sviluppo integrato, il **Editor di codice** implementa i membri di classe richiesti da `TestInterface` quando si preme INVIO, ed è possibile ignorare il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3.  <span data-ttu-id="8e7e6-123">Se non si lavora all'interno dell'ambiente di sviluppo integrato, è necessario implementare tutti i membri dell'interfaccia `MyInterface`.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="8e7e6-124">Aggiungere il seguente codice al `ImplementationClass` implementare `Event1`, `Method1`, e `Prop1`:</span><span class="sxs-lookup"><span data-stu-id="8e7e6-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     <span data-ttu-id="8e7e6-125">Il `Implements` istruzione assegna un nome di interfaccia e un membro di interfaccia implementato.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4.  <span data-ttu-id="8e7e6-126">Completare la definizione di `Prop1` aggiungendo un campo privato per la classe che è archiviato il valore della proprietà:</span><span class="sxs-lookup"><span data-stu-id="8e7e6-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     <span data-ttu-id="8e7e6-127">Restituisce il valore di `pval` dalla proprietà get.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     <span data-ttu-id="8e7e6-128">Impostare il valore di `pval` nel set di proprietà della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5.  <span data-ttu-id="8e7e6-129">Completare la definizione di `Method1` aggiungendo il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="8e7e6-130">Per testare l'implementazione dell'interfaccia</span><span class="sxs-lookup"><span data-stu-id="8e7e6-130">To test the implementation of the interface</span></span>
  
1.  <span data-ttu-id="8e7e6-131">Fare doppio clic su form di avvio per il progetto nel **Esplora**, fare clic su **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="8e7e6-132">L'editor visualizza la classe del form di avvio.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="8e7e6-133">Per impostazione predefinita, viene chiamato il form di avvio `Form1`.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-133">By default, the startup form is called `Form1`.</span></span>  
  
2.  <span data-ttu-id="8e7e6-134">Aggiungere il seguente `testInstance` campo la `Form1` classe:</span><span class="sxs-lookup"><span data-stu-id="8e7e6-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     <span data-ttu-id="8e7e6-135">Dichiarando `testInstance` come `WithEvents`, `Form1` classe consente di gestire gli eventi.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3.  <span data-ttu-id="8e7e6-136">Aggiungere il seguente gestore eventi per il `Form1` classe per gestire gli eventi generati da `testInstance`:</span><span class="sxs-lookup"><span data-stu-id="8e7e6-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4.  <span data-ttu-id="8e7e6-137">Aggiungere una subroutine denominata `Test` per la `Form1` classe per testare la classe di implementazione:</span><span class="sxs-lookup"><span data-stu-id="8e7e6-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     <span data-ttu-id="8e7e6-138">Il `Test` procedura consente di creare un'istanza della classe che implementa `MyInterface`, assegna l'istanza di `testInstance` imposta una proprietà, campo e viene eseguito un metodo tramite l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5.  <span data-ttu-id="8e7e6-139">Aggiungere codice per chiamare il `Test` stored procedure di `Form1 Load` routine del form di avvio:</span><span class="sxs-lookup"><span data-stu-id="8e7e6-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6.  <span data-ttu-id="8e7e6-140">Eseguire il `Test` procedura premendo F5.</span><span class="sxs-lookup"><span data-stu-id="8e7e6-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="8e7e6-141">Viene visualizzato il messaggio "Prop1 è stato impostato su 9".</span><span class="sxs-lookup"><span data-stu-id="8e7e6-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="8e7e6-142">Viene visualizzato dopo aver selezionato OK, il messaggio "il parametro X per Method1 is 5".</span><span class="sxs-lookup"><span data-stu-id="8e7e6-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="8e7e6-143">Fare clic su OK e viene visualizzato il messaggio "il gestore dell'evento ha rilevato l'evento".</span><span class="sxs-lookup"><span data-stu-id="8e7e6-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e7e6-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e7e6-144">See also</span></span>

 [<span data-ttu-id="8e7e6-145">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="8e7e6-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="8e7e6-146">Interfacce</span><span class="sxs-lookup"><span data-stu-id="8e7e6-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [<span data-ttu-id="8e7e6-147">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="8e7e6-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="8e7e6-148">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="8e7e6-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)  