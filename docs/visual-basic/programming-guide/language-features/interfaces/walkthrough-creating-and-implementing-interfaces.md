---
title: Creazione e implementazione di interfacce (Visual Basic) | Documenti di Microsoft
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
- interfaces, walkthroughs
- interfaces, testing
- interface implementation, walkthrough
- interfaces, creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: 22
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
ms.openlocfilehash: ef1ec16005bf0a7967d396054ae23c1023143c2a
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="8bd43-102">Procedura dettagliata: creazione e implementazione di interfacce (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8bd43-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>
<span data-ttu-id="8bd43-103">Interfacce descrivono le caratteristiche di proprietà, metodi ed eventi, ma i dettagli relativi all'implementazione fino a strutture o classi.</span><span class="sxs-lookup"><span data-stu-id="8bd43-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="8bd43-104">Questa procedura dettagliata viene illustrato come dichiarare e implementare un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8bd43-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8bd43-105">Questa procedura dettagliata non fornisce informazioni su come creare un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="8bd43-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-an-interface"></a><span data-ttu-id="8bd43-106">Per definire un'interfaccia</span><span class="sxs-lookup"><span data-stu-id="8bd43-106">To define an interface</span></span>  
  
1.  <span data-ttu-id="8bd43-107">Aprire un nuovo [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] progetto applicazione Windows.</span><span class="sxs-lookup"><span data-stu-id="8bd43-107">Open a new [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="8bd43-108">Aggiungere un nuovo modulo per il progetto facendo clic su **Aggiungi modulo** sul **Project** menu.</span><span class="sxs-lookup"><span data-stu-id="8bd43-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="8bd43-109">Nome del nuovo modulo `Module1.vb` e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8bd43-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="8bd43-110">Viene visualizzato il codice per il nuovo modulo.</span><span class="sxs-lookup"><span data-stu-id="8bd43-110">The code for the new module is displayed.</span></span>  
  
4.  <span data-ttu-id="8bd43-111">Definire un'interfaccia denominata `TestInterface` all'interno di `Module1` digitando `Interface TestInterface` tra il `Module` e `End Module` istruzioni e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="8bd43-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="8bd43-112">Il **Editor di codice** rientri il `Interface` (parola chiave) e aggiunge un `End Interface` istruzione in modo da formare un blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="8bd43-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5.  <span data-ttu-id="8bd43-113">Definire un proprietà, metodi ed eventi per l'interfaccia inserendo il codice seguente tra i `Interface` e `End Interface` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="8bd43-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     <span data-ttu-id="8bd43-114">[!code-vb[&#98; VbVbalrOOP](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bd43-114">[!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="8bd43-115">Implementazione</span><span class="sxs-lookup"><span data-stu-id="8bd43-115">Implementation</span></span>  
 <span data-ttu-id="8bd43-116">È possibile notare che la sintassi utilizzata per dichiarare i membri di interfaccia è diversa da quella utilizzata per dichiarare i membri della classe.</span><span class="sxs-lookup"><span data-stu-id="8bd43-116">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="8bd43-117">La differenza è dovuta al fatto che le interfacce non possono contenere codice di implementazione.</span><span class="sxs-lookup"><span data-stu-id="8bd43-117">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
#### <a name="to-implement-the-interface"></a><span data-ttu-id="8bd43-118">Per implementare l'interfaccia</span><span class="sxs-lookup"><span data-stu-id="8bd43-118">To implement the interface</span></span>  
  
1.  <span data-ttu-id="8bd43-119">Aggiungere una classe denominata `ImplementationClass` aggiungendo l'istruzione seguente alle `Module1`, dopo il `End Interface` istruzione ma prima che il `End Module` istruzione e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="8bd43-119">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     <span data-ttu-id="8bd43-120">[!code-vb[VbVbalrOOP&#99;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bd43-120">[!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]</span></span>  
  
     <span data-ttu-id="8bd43-121">Se si lavora all'interno dell'ambiente di sviluppo integrato, il **Editor di codice** fornisce un corrispondente `End Class` istruzione quando si preme INVIO.</span><span class="sxs-lookup"><span data-stu-id="8bd43-121">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2.  <span data-ttu-id="8bd43-122">Aggiungere il codice seguente `Implements` istruzione `ImplementationClass`, quali nome dell'interfaccia implementata dalla classe:</span><span class="sxs-lookup"><span data-stu-id="8bd43-122">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     <span data-ttu-id="8bd43-123">[!code-vb[VbVbalrOOP&#100;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bd43-123">[!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]</span></span>  
  
     <span data-ttu-id="8bd43-124">Quando elencata separatamente da altri elementi nella parte superiore di una classe o struttura, il `Implements` istruzione indica che la classe o struttura implementa un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8bd43-124">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="8bd43-125">Se si lavora all'interno dell'ambiente di sviluppo integrato, il **Editor di codice** implementa i membri di classe richiesti da `TestInterface` quando si preme INVIO, e si può ignorare il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="8bd43-125">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3.  <span data-ttu-id="8bd43-126">Se non si lavora all'interno dell'ambiente di sviluppo integrato, è necessario implementare tutti i membri dell'interfaccia `MyInterface`.</span><span class="sxs-lookup"><span data-stu-id="8bd43-126">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="8bd43-127">Aggiungere il codice seguente a `ImplementationClass` implementare `Event1`, `Method1`, e `Prop1`:</span><span class="sxs-lookup"><span data-stu-id="8bd43-127">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     <span data-ttu-id="8bd43-128">[!code-vb[VbVbalrOOP&#101;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bd43-128">[!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]</span></span>  
  
     <span data-ttu-id="8bd43-129">Il `Implements` istruzione denomina l'interfaccia e un membro di interfaccia implementati.</span><span class="sxs-lookup"><span data-stu-id="8bd43-129">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4.  <span data-ttu-id="8bd43-130">Completare la definizione di `Prop1` aggiungendo un campo privato per la classe che è archiviato il valore della proprietà:</span><span class="sxs-lookup"><span data-stu-id="8bd43-130">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     <span data-ttu-id="8bd43-131">[!code-vb[&#102; VbVbalrOOP](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bd43-131">[!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]</span></span>  
  
     <span data-ttu-id="8bd43-132">Restituisce il valore di `pval` dalla proprietà get.</span><span class="sxs-lookup"><span data-stu-id="8bd43-132">Return the value of the `pval` from the property get accessor.</span></span>  
  
     <span data-ttu-id="8bd43-133">[!code-vb[VbVbalrOOP&#103;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bd43-133">[!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]</span></span>  
  
     <span data-ttu-id="8bd43-134">Impostare il valore di `pval` nel set di proprietà della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="8bd43-134">Set the value of `pval` in the property set accessor.</span></span>  
  
     <span data-ttu-id="8bd43-135">[!code-vb[&#104; VbVbalrOOP](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bd43-135">[!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]</span></span>  
  
5.  <span data-ttu-id="8bd43-136">Completare la definizione di `Method1` aggiungendo il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="8bd43-136">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     <span data-ttu-id="8bd43-137">[!code-vb[&#105; VbVbalrOOP](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bd43-137">[!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]</span></span>  
  
#### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="8bd43-138">Per testare l'implementazione dell'interfaccia</span><span class="sxs-lookup"><span data-stu-id="8bd43-138">To test the implementation of the interface</span></span>  
  
1.  <span data-ttu-id="8bd43-139">Fare doppio clic su form di avvio per il progetto nel **Esplora**, fare clic su **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="8bd43-139">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="8bd43-140">L'editor visualizza la classe del form di avvio.</span><span class="sxs-lookup"><span data-stu-id="8bd43-140">The editor displays the class for your startup form.</span></span> <span data-ttu-id="8bd43-141">Per impostazione predefinita, viene chiamato il form di avvio `Form1`.</span><span class="sxs-lookup"><span data-stu-id="8bd43-141">By default, the startup form is called `Form1`.</span></span>  
  
2.  <span data-ttu-id="8bd43-142">Aggiungere il codice seguente `testInstance` campo la `Form1` classe:</span><span class="sxs-lookup"><span data-stu-id="8bd43-142">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     <span data-ttu-id="8bd43-143">[!code-vb[&#120; VbVbalrOOP](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bd43-143">[!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]</span></span>  
  
     <span data-ttu-id="8bd43-144">Dichiarando `testInstance` come `WithEvents`, `Form1` classe può gestire gli eventi.</span><span class="sxs-lookup"><span data-stu-id="8bd43-144">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3.  <span data-ttu-id="8bd43-145">Aggiungere il seguente gestore eventi per il `Form1` classe per gestire gli eventi generati da `testInstance`:</span><span class="sxs-lookup"><span data-stu-id="8bd43-145">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     <span data-ttu-id="8bd43-146">[!code-vb[&#106; VbVbalrOOP](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bd43-146">[!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]</span></span>  
  
4.  <span data-ttu-id="8bd43-147">Aggiungere una subroutine denominata `Test` per la `Form1` classe da testare l'implementazione della classe:</span><span class="sxs-lookup"><span data-stu-id="8bd43-147">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     <span data-ttu-id="8bd43-148">[!code-vb[&#107; VbVbalrOOP](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bd43-148">[!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]</span></span>  
  
     <span data-ttu-id="8bd43-149">Il `Test` procedura crea un'istanza della classe che implementa `MyInterface`, assegna l'istanza di `testInstance` imposta una proprietà, campo e viene eseguito un metodo tramite l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8bd43-149">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5.  <span data-ttu-id="8bd43-150">Aggiungere codice per chiamare il `Test` procedura il `Form1 Load` routine del form di avvio:</span><span class="sxs-lookup"><span data-stu-id="8bd43-150">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     <span data-ttu-id="8bd43-151">[!code-vb[&#108; VbVbalrOOP](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bd43-151">[!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]</span></span>  
  
6.  <span data-ttu-id="8bd43-152">Eseguire il `Test` procedura premendo F5.</span><span class="sxs-lookup"><span data-stu-id="8bd43-152">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="8bd43-153">Viene visualizzato il messaggio "Prop1 è stato impostato su 9".</span><span class="sxs-lookup"><span data-stu-id="8bd43-153">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="8bd43-154">Viene visualizzato dopo aver fatto clic su OK, il messaggio "il parametro X per Method1 is 5".</span><span class="sxs-lookup"><span data-stu-id="8bd43-154">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="8bd43-155">Fare clic su OK e viene visualizzato il messaggio "il gestore dell'evento rilevata l'evento".</span><span class="sxs-lookup"><span data-stu-id="8bd43-155">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd43-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bd43-156">See Also</span></span>  
 <span data-ttu-id="8bd43-157">[Implements (istruzione)](../../../../visual-basic/language-reference/statements/implements-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8bd43-157">[Implements Statement](../../../../visual-basic/language-reference/statements/implements-statement.md) </span></span>  
<span data-ttu-id="8bd43-158"> [Interfacce](../../../../visual-basic/programming-guide/language-features/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="8bd43-158"> [Interfaces](../../../../visual-basic/programming-guide/language-features/interfaces/index.md) </span></span>  
<span data-ttu-id="8bd43-159"> [Istruzione Interface](../../../../visual-basic/language-reference/statements/interface-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8bd43-159"> [Interface Statement](../../../../visual-basic/language-reference/statements/interface-statement.md) </span></span>  
<span data-ttu-id="8bd43-160"> [Istruzione Event](../../../../visual-basic/language-reference/statements/event-statement.md)</span><span class="sxs-lookup"><span data-stu-id="8bd43-160"> [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md)</span></span>

