---
title: Creare una Windows Forms Application dalla riga di comando
titleSuffix: ''
description: Informazioni su come completare i passaggi di base per creare ed eseguire un Windows Forms Application dalla riga di comando.
ms.date: 03/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
ms.openlocfilehash: b63bf884b9fd03a0510c7f240f19d7a14196971a
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903454"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a><span data-ttu-id="b8558-103">Procedura: creare una Windows Forms Application dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="b8558-103">How to: Create a Windows Forms application from the command line</span></span>

<span data-ttu-id="b8558-104">Le procedure seguenti descrivono i passaggi di base che è necessario completare per creare ed eseguire un'applicazione Windows Forms dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b8558-104">The following procedures describe the basic steps that you must complete to create and run a Windows Forms application from the command line.</span></span> <span data-ttu-id="b8558-105">Esiste un supporto completo per queste procedure in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b8558-105">There is extensive support for these procedures in Visual Studio.</span></span>  <span data-ttu-id="b8558-106">Vedere anche [procedura dettagliata: hosting di un controllo Windows Forms in WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="b8558-106">Also see [Walkthrough: Hosting a Windows Forms Control in WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>
  
## <a name="procedure"></a><span data-ttu-id="b8558-107">Procedura</span><span class="sxs-lookup"><span data-stu-id="b8558-107">Procedure</span></span>  
  
#### <a name="to-create-the-form"></a><span data-ttu-id="b8558-108">Per creare il form</span><span class="sxs-lookup"><span data-stu-id="b8558-108">To create the form</span></span>  
  
1. <span data-ttu-id="b8558-109">In un file di codice vuoto, digitare le `Imports` seguenti `using` istruzioni o:</span><span class="sxs-lookup"><span data-stu-id="b8558-109">In an empty code file, type the following `Imports` or `using` statements:</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="b8558-110">Dichiarare una classe denominata `Form1` che eredita dalla classe form:</span><span class="sxs-lookup"><span data-stu-id="b8558-110">Declare a class named `Form1` that inherits from the Form class:</span></span>
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3. <span data-ttu-id="b8558-111">Creare un costruttore senza parametri per `Form1` .</span><span class="sxs-lookup"><span data-stu-id="b8558-111">Create a parameterless constructor for `Form1`.</span></span>
  
     <span data-ttu-id="b8558-112">Si aggiungerà il resto del codice al costruttore in una procedura successiva.</span><span class="sxs-lookup"><span data-stu-id="b8558-112">You will add more code to the constructor in a subsequent procedure.</span></span>
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4. <span data-ttu-id="b8558-113">Aggiungere un metodo `Main` alla classe.</span><span class="sxs-lookup"><span data-stu-id="b8558-113">Add a `Main` method to the class.</span></span>
  
    1. <span data-ttu-id="b8558-114">Applicare al <xref:System.STAThreadAttribute> `Main` Metodo C# per specificare che l'Windows Forms Application è un Apartment a thread singolo.</span><span class="sxs-lookup"><span data-stu-id="b8558-114">Apply the <xref:System.STAThreadAttribute> to the C# `Main` method to specify your Windows Forms application is a single-threaded apartment.</span></span> <span data-ttu-id="b8558-115">L'attributo non è necessario in Visual Basic, poiché le applicazioni Windows Forms sviluppate con Visual Basic usano un modello di Apartment a thread singolo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b8558-115">(The attribute is not necessary in Visual Basic, since Windows forms applications developed with Visual Basic use a single-threaded apartment model by default.)</span></span>  
  
    2. <span data-ttu-id="b8558-116">Chiamare <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> per applicare gli stili del sistema operativo all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b8558-116">Call <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> to apply operating system styles to your application.</span></span>  
  
    3. <span data-ttu-id="b8558-117">Creare un'istanza del form ed eseguirla.</span><span class="sxs-lookup"><span data-stu-id="b8558-117">Create an instance of the form and run it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a><span data-ttu-id="b8558-118">Per compilare l'applicazione ed eseguirla</span><span class="sxs-lookup"><span data-stu-id="b8558-118">To compile and run the application</span></span>  
  
1. <span data-ttu-id="b8558-119">Al prompt dei comandi di .NET Framework passare alla directory creata per la classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="b8558-119">At the .NET Framework command prompt, navigate to the directory you created the `Form1` class.</span></span>  
  
2. <span data-ttu-id="b8558-120">Compilare il form.</span><span class="sxs-lookup"><span data-stu-id="b8558-120">Compile the form.</span></span>  
  
    - <span data-ttu-id="b8558-121">Se si usa C#, digitare:`csc form1.cs`</span><span class="sxs-lookup"><span data-stu-id="b8558-121">If you are using C#, type: `csc form1.cs`</span></span>  
  
         `-or-`  
  
    - <span data-ttu-id="b8558-122">Se si utilizza Visual Basic, digitare:`vbc form1.vb`</span><span class="sxs-lookup"><span data-stu-id="b8558-122">If you are using Visual Basic, type: `vbc form1.vb`</span></span>  
  
3. <span data-ttu-id="b8558-123">Al prompt dei comandi digitare: `Form1.exe`</span><span class="sxs-lookup"><span data-stu-id="b8558-123">At the command prompt, type: `Form1.exe`</span></span>  
  
## <a name="adding-a-control-and-handling-an-event"></a><span data-ttu-id="b8558-124">Aggiunta di un controllo e gestione di un evento</span><span class="sxs-lookup"><span data-stu-id="b8558-124">Adding a control and handling an event</span></span>

<span data-ttu-id="b8558-125">I passaggi della precedente procedura hanno illustrato come creare un Windows Form di base che viene compilato ed eseguito.</span><span class="sxs-lookup"><span data-stu-id="b8558-125">The previous procedure steps demonstrated how to just create a basic Windows Form that compiles and runs.</span></span> <span data-ttu-id="b8558-126">La procedura successiva mostrerà come creare e aggiungere un controllo al form e come gestire un evento per il controllo.</span><span class="sxs-lookup"><span data-stu-id="b8558-126">The next procedure will show you how to create and add a control to the form, and handle an event for the control.</span></span> <span data-ttu-id="b8558-127">Per ulteriori informazioni sui controlli che è possibile aggiungere a Windows Forms, vedere [controlli di Windows Forms](./controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="b8558-127">For more information about the controls you can add to Windows Forms, see [Windows Forms Controls](./controls/index.md).</span></span>
  
 <span data-ttu-id="b8558-128">Oltre a saper creare applicazioni Windows Forms, è consigliabile conoscere la programmazione basata sugli eventi e come gestire l'input utente.</span><span class="sxs-lookup"><span data-stu-id="b8558-128">In addition to understanding how to create Windows Forms applications, you should understand event-based programming and how to handle user input.</span></span> <span data-ttu-id="b8558-129">Per altre informazioni, vedere [creazione di gestori eventi in Windows Forms](creating-event-handlers-in-windows-forms.md)e [gestione dell'input dell'utente](./controls/handling-user-input.md)</span><span class="sxs-lookup"><span data-stu-id="b8558-129">For more information, see [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md), and [Handling User Input](./controls/handling-user-input.md)</span></span>  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a><span data-ttu-id="b8558-130">Per dichiarare un pulsante e gestirne l'evento click</span><span class="sxs-lookup"><span data-stu-id="b8558-130">To declare a button control and handle its click event</span></span>  
  
1. <span data-ttu-id="b8558-131">Dichiarare un pulsante denominato `button1`.</span><span class="sxs-lookup"><span data-stu-id="b8558-131">Declare a button control named `button1`.</span></span>  
  
2. <span data-ttu-id="b8558-132">Nel costruttore creare il pulsante e impostarne le proprietà <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> e <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="b8558-132">In the constructor, create the button and set its <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Text%2A> properties.</span></span>  
  
3. <span data-ttu-id="b8558-133">Aggiungere il pulsante al form.</span><span class="sxs-lookup"><span data-stu-id="b8558-133">Add the button to the form.</span></span>  
  
     <span data-ttu-id="b8558-134">Nell'esempio di codice riportato di seguito viene illustrato come dichiarare il controllo Button:</span><span class="sxs-lookup"><span data-stu-id="b8558-134">The following code example demonstrates how to declare the button control:</span></span>
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4. <span data-ttu-id="b8558-135">Creare un metodo per gestire l'evento <xref:System.Windows.Forms.Control.Click> per il pulsante.</span><span class="sxs-lookup"><span data-stu-id="b8558-135">Create a method to handle the <xref:System.Windows.Forms.Control.Click> event for the button.</span></span>  
  
5. <span data-ttu-id="b8558-136">Nel gestore dell'evento click visualizzare un oggetto <xref:System.Windows.Forms.MessageBox> con il messaggio "Hello World".</span><span class="sxs-lookup"><span data-stu-id="b8558-136">In the click event handler, display a <xref:System.Windows.Forms.MessageBox> with the message, "Hello World".</span></span>  
  
     <span data-ttu-id="b8558-137">Nell'esempio di codice riportato di seguito viene illustrato come gestire l'evento click del controllo Button:</span><span class="sxs-lookup"><span data-stu-id="b8558-137">The following code example demonstrates how to handle the button control's click event:</span></span>
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6. <span data-ttu-id="b8558-138">Associare l'evento <xref:System.Windows.Forms.Control.Click> al metodo creato.</span><span class="sxs-lookup"><span data-stu-id="b8558-138">Associate the <xref:System.Windows.Forms.Control.Click> event with the method you created.</span></span>  
  
     <span data-ttu-id="b8558-139">Nell'esempio di codice seguente viene illustrato come associare l'evento al metodo.</span><span class="sxs-lookup"><span data-stu-id="b8558-139">The following code example demonstrates how to associate the event with the method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7. <span data-ttu-id="b8558-140">Compilare ed eseguire l'applicazione come descritto nella precedente procedura.</span><span class="sxs-lookup"><span data-stu-id="b8558-140">Compile and run the application as described in the previous procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8558-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8558-141">Example</span></span>  

<span data-ttu-id="b8558-142">L'esempio di codice seguente è l'esempio completo delle procedure precedenti:</span><span class="sxs-lookup"><span data-stu-id="b8558-142">The following code example is the complete example from the previous procedures:</span></span>
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b8558-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8558-143">See also</span></span>

- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Control>
- [<span data-ttu-id="b8558-144">Modifica dell'aspetto di Windows Form</span><span class="sxs-lookup"><span data-stu-id="b8558-144">Changing the Appearance of Windows Forms</span></span>](changing-the-appearance-of-windows-forms.md)
- [<span data-ttu-id="b8558-145">Miglioramento delle applicazioni Windows Form</span><span class="sxs-lookup"><span data-stu-id="b8558-145">Enhancing Windows Forms Applications</span></span>](./advanced/index.md)
- [<span data-ttu-id="b8558-146">Introduzione con Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b8558-146">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
