---
title: Creare un'applicazione Windows Form dalla riga di comandoCreate a Windows Forms application from the command line
titleSuffix: ''
ms.date: 03/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
ms.openlocfilehash: 7bd3add526a6b60d628b05d46eca22ce407c36b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181982"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a><span data-ttu-id="a06dd-102">Procedura: creare un'applicazione Windows Form dalla riga di comandoHow to: Create a Windows Forms application from the command line</span><span class="sxs-lookup"><span data-stu-id="a06dd-102">How to: Create a Windows Forms application from the command line</span></span>

<span data-ttu-id="a06dd-103">Le procedure seguenti descrivono i passaggi di base che è necessario completare per creare ed eseguire un'applicazione Windows Forms dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="a06dd-103">The following procedures describe the basic steps that you must complete to create and run a Windows Forms application from the command line.</span></span> <span data-ttu-id="a06dd-104">Esiste un supporto completo per queste procedure in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a06dd-104">There is extensive support for these procedures in Visual Studio.</span></span>  <span data-ttu-id="a06dd-105">Vedere [anche Procedura dettagliata: hosting di un controllo Windows Form in WPF.](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)</span><span class="sxs-lookup"><span data-stu-id="a06dd-105">Also see [Walkthrough: Hosting a Windows Forms Control in WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>
  
## <a name="procedure"></a><span data-ttu-id="a06dd-106">Procedura</span><span class="sxs-lookup"><span data-stu-id="a06dd-106">Procedure</span></span>  
  
#### <a name="to-create-the-form"></a><span data-ttu-id="a06dd-107">Per creare il form</span><span class="sxs-lookup"><span data-stu-id="a06dd-107">To create the form</span></span>  
  
1. <span data-ttu-id="a06dd-108">In un file di codice `Imports` `using` vuoto digitare le istruzioni seguenti:In an empty code file, type the following or statements:</span><span class="sxs-lookup"><span data-stu-id="a06dd-108">In an empty code file, type the following `Imports` or `using` statements:</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="a06dd-109">Dichiarare una `Form1` classe denominata che eredita dalla classe Form:</span><span class="sxs-lookup"><span data-stu-id="a06dd-109">Declare a class named `Form1` that inherits from the Form class:</span></span>
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3. <span data-ttu-id="a06dd-110">Creare un costruttore `Form1`senza parametri per .</span><span class="sxs-lookup"><span data-stu-id="a06dd-110">Create a parameterless constructor for `Form1`.</span></span>
  
     <span data-ttu-id="a06dd-111">Si aggiungerà il resto del codice al costruttore in una procedura successiva.</span><span class="sxs-lookup"><span data-stu-id="a06dd-111">You will add more code to the constructor in a subsequent procedure.</span></span>
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4. <span data-ttu-id="a06dd-112">Aggiungere un metodo `Main` alla classe.</span><span class="sxs-lookup"><span data-stu-id="a06dd-112">Add a `Main` method to the class.</span></span>
  
    1. <span data-ttu-id="a06dd-113">Applicare <xref:System.STAThreadAttribute> il per `Main` il metodo di C , per specificare l'applicazione Windows Form è un apartment a thread singolo.</span><span class="sxs-lookup"><span data-stu-id="a06dd-113">Apply the <xref:System.STAThreadAttribute> to the C# `Main` method to specify your Windows Forms application is a single-threaded apartment.</span></span> <span data-ttu-id="a06dd-114">L'attributo non è necessario in Visual Basic, poiché le applicazioni Windows Form sviluppate con Visual Basic utilizzano un modello di apartment a thread singolo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a06dd-114">(The attribute is not necessary in Visual Basic, since Windows forms applications developed with Visual Basic use a single-threaded apartment model by default.)</span></span>  
  
    2. <span data-ttu-id="a06dd-115">Chiamare <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> per applicare gli stili del sistema operativo all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a06dd-115">Call <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> to apply operating system styles to your application.</span></span>  
  
    3. <span data-ttu-id="a06dd-116">Creare un'istanza del form ed eseguirla.</span><span class="sxs-lookup"><span data-stu-id="a06dd-116">Create an instance of the form and run it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a><span data-ttu-id="a06dd-117">Per compilare l'applicazione ed eseguirla</span><span class="sxs-lookup"><span data-stu-id="a06dd-117">To compile and run the application</span></span>  
  
1. <span data-ttu-id="a06dd-118">Al prompt dei comandi di .NET Framework passare alla directory creata per la classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="a06dd-118">At the .NET Framework command prompt, navigate to the directory you created the `Form1` class.</span></span>  
  
2. <span data-ttu-id="a06dd-119">Compilare il form.</span><span class="sxs-lookup"><span data-stu-id="a06dd-119">Compile the form.</span></span>  
  
    - <span data-ttu-id="a06dd-120">Se si utilizza C , digitare:`csc form1.cs`</span><span class="sxs-lookup"><span data-stu-id="a06dd-120">If you are using C#, type: `csc form1.cs`</span></span>  
  
         `-or-`  
  
    - <span data-ttu-id="a06dd-121">Se si utilizza Visual Basic, digitare:`vbc form1.vb`</span><span class="sxs-lookup"><span data-stu-id="a06dd-121">If you are using Visual Basic, type: `vbc form1.vb`</span></span>  
  
3. <span data-ttu-id="a06dd-122">Al prompt dei comandi digitare: `Form1.exe`</span><span class="sxs-lookup"><span data-stu-id="a06dd-122">At the command prompt, type: `Form1.exe`</span></span>  
  
## <a name="adding-a-control-and-handling-an-event"></a><span data-ttu-id="a06dd-123">Aggiunta di un controllo e gestione di un evento</span><span class="sxs-lookup"><span data-stu-id="a06dd-123">Adding a control and handling an event</span></span>

<span data-ttu-id="a06dd-124">I passaggi della precedente procedura hanno illustrato come creare un Windows Form di base che viene compilato ed eseguito.</span><span class="sxs-lookup"><span data-stu-id="a06dd-124">The previous procedure steps demonstrated how to just create a basic Windows Form that compiles and runs.</span></span> <span data-ttu-id="a06dd-125">La procedura successiva mostrerà come creare e aggiungere un controllo al form e come gestire un evento per il controllo.</span><span class="sxs-lookup"><span data-stu-id="a06dd-125">The next procedure will show you how to create and add a control to the form, and handle an event for the control.</span></span> <span data-ttu-id="a06dd-126">Per ulteriori informazioni sui controlli che è possibile aggiungere a Windows Form, vedere [Controlli Windows Form](./controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="a06dd-126">For more information about the controls you can add to Windows Forms, see [Windows Forms Controls](./controls/index.md).</span></span>
  
 <span data-ttu-id="a06dd-127">Oltre a saper creare applicazioni Windows Forms, è consigliabile conoscere la programmazione basata sugli eventi e come gestire l'input utente.</span><span class="sxs-lookup"><span data-stu-id="a06dd-127">In addition to understanding how to create Windows Forms applications, you should understand event-based programming and how to handle user input.</span></span> <span data-ttu-id="a06dd-128">Per ulteriori informazioni, vedere [Creazione di gestori eventi in Windows Form](creating-event-handlers-in-windows-forms.md)e Gestione [dell'input dell'utente](./controls/handling-user-input.md)</span><span class="sxs-lookup"><span data-stu-id="a06dd-128">For more information, see [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md), and [Handling User Input](./controls/handling-user-input.md)</span></span>  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a><span data-ttu-id="a06dd-129">Per dichiarare un pulsante e gestirne l'evento click</span><span class="sxs-lookup"><span data-stu-id="a06dd-129">To declare a button control and handle its click event</span></span>  
  
1. <span data-ttu-id="a06dd-130">Dichiarare un pulsante denominato `button1`.</span><span class="sxs-lookup"><span data-stu-id="a06dd-130">Declare a button control named `button1`.</span></span>  
  
2. <span data-ttu-id="a06dd-131">Nel costruttore creare il pulsante e impostarne le proprietà <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> e <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="a06dd-131">In the constructor, create the button and set its <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Text%2A> properties.</span></span>  
  
3. <span data-ttu-id="a06dd-132">Aggiungere il pulsante al form.</span><span class="sxs-lookup"><span data-stu-id="a06dd-132">Add the button to the form.</span></span>  
  
     <span data-ttu-id="a06dd-133">Esempio di codice seguente viene illustrato come dichiarare il controllo pulsante:The following code example demonstrates how to declare the button control:</span><span class="sxs-lookup"><span data-stu-id="a06dd-133">The following code example demonstrates how to declare the button control:</span></span>
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4. <span data-ttu-id="a06dd-134">Creare un metodo per gestire l'evento <xref:System.Windows.Forms.Control.Click> per il pulsante.</span><span class="sxs-lookup"><span data-stu-id="a06dd-134">Create a method to handle the <xref:System.Windows.Forms.Control.Click> event for the button.</span></span>  
  
5. <span data-ttu-id="a06dd-135">Nel gestore dell'evento click visualizzare un oggetto <xref:System.Windows.Forms.MessageBox> con il messaggio "Hello World".</span><span class="sxs-lookup"><span data-stu-id="a06dd-135">In the click event handler, display a <xref:System.Windows.Forms.MessageBox> with the message, "Hello World".</span></span>  
  
     <span data-ttu-id="a06dd-136">Esempio di codice seguente viene illustrato come gestire l'evento click del controllo pulsante:The following code example demonstrates how to handle the button control's click event:</span><span class="sxs-lookup"><span data-stu-id="a06dd-136">The following code example demonstrates how to handle the button control's click event:</span></span>
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6. <span data-ttu-id="a06dd-137">Associare l'evento <xref:System.Windows.Forms.Control.Click> al metodo creato.</span><span class="sxs-lookup"><span data-stu-id="a06dd-137">Associate the <xref:System.Windows.Forms.Control.Click> event with the method you created.</span></span>  
  
     <span data-ttu-id="a06dd-138">Nell'esempio di codice seguente viene illustrato come associare l'evento al metodo.</span><span class="sxs-lookup"><span data-stu-id="a06dd-138">The following code example demonstrates how to associate the event with the method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7. <span data-ttu-id="a06dd-139">Compilare ed eseguire l'applicazione come descritto nella precedente procedura.</span><span class="sxs-lookup"><span data-stu-id="a06dd-139">Compile and run the application as described in the previous procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a06dd-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="a06dd-140">Example</span></span>  

<span data-ttu-id="a06dd-141">L'esempio di codice seguente è l'esempio completo delle procedure precedenti:The following code example is the complete example from the previous procedures:</span><span class="sxs-lookup"><span data-stu-id="a06dd-141">The following code example is the complete example from the previous procedures:</span></span>
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a06dd-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a06dd-142">See also</span></span>

- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Control>
- [<span data-ttu-id="a06dd-143">Modifica dell'aspetto di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a06dd-143">Changing the Appearance of Windows Forms</span></span>](changing-the-appearance-of-windows-forms.md)
- [<span data-ttu-id="a06dd-144">Miglioramento delle applicazioni Windows Form</span><span class="sxs-lookup"><span data-stu-id="a06dd-144">Enhancing Windows Forms Applications</span></span>](./advanced/index.md)
- [<span data-ttu-id="a06dd-145">Guida introduttiva a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a06dd-145">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
