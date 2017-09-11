---
title: "Poiché questa chiamata non può essere attesa, il metodo corrente continua prima del completamento della chiamata di | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42358
- vbc42358
helpviewer_keywords:
- BC42358
ms.assetid: 43342515-c3c8-4155-9263-c302afabcbc2
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: acee06829c246fbff866bfe188d6685f7cd8a263
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="because-this-call-is-not-awaited-the-current-method-continues-to-run-before-the-call-is-completed"></a><span data-ttu-id="bd240-102">Poiché la chiamata non può essere attesa, l'esecuzione del metodo corrente continua prima del completamento della chiamata</span><span class="sxs-lookup"><span data-stu-id="bd240-102">Because this call is not awaited, the current method continues to run before the call is completed</span></span>
<span data-ttu-id="bd240-103">Non è possibile attendere la chiamata, pertanto l'esecuzione del metodo corrente continuerà prima del completamento della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bd240-103">Because this call is not awaited, execution of the current method continues before the call is completed.</span></span> <span data-ttu-id="bd240-104">È possibile applicare l'operatore "Await" al risultato della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bd240-104">Consider applying the 'Await' operator to the result of the call.</span></span>  
  
 <span data-ttu-id="bd240-105">Il metodo corrente viene chiamato un metodo asincrono che restituisce un <xref:System.Threading.Tasks.Task>o <xref:System.Threading.Tasks.Task%601>e non si applica il [Await](../../../visual-basic/language-reference/operators/await-operator.md) nel risultato.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="bd240-105">The current method calls an async method that returns a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601> and doesn’t apply the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator to the result.</span></span> <span data-ttu-id="bd240-106">Con la chiamata al metodo asincrono viene avviata un'attività asincrona.</span><span class="sxs-lookup"><span data-stu-id="bd240-106">The call to the async method starts an asynchronous task.</span></span> <span data-ttu-id="bd240-107">Tuttavia, poiché non viene applicato alcun operatore `Await` , l'esecuzione del programma continua senza attendere il completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="bd240-107">However, because no `Await` operator is applied, the program continues without waiting for the task to complete.</span></span> <span data-ttu-id="bd240-108">Nella maggior parte dei casi questo comportamento non è quello previsto.</span><span class="sxs-lookup"><span data-stu-id="bd240-108">In most cases, that behavior isn't expected.</span></span> <span data-ttu-id="bd240-109">Di solito altri aspetti del metodo chiamante dipendono dai risultati della chiamata o, come minimo, si prevede che il metodo chiamato venga completato prima della restituzione da parte del metodo contenente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bd240-109">Usually other aspects of the calling method depend on the results of the call or, minimally, the called method is expected to complete before you return from the method that contains the call.</span></span>  
  
 <span data-ttu-id="bd240-110">Un problema ugualmente importante riguarda cosa accade con le eccezioni generate nel metodo asincrono richiamato.</span><span class="sxs-lookup"><span data-stu-id="bd240-110">An equally important issue is what happens with exceptions that are raised in the called async method.</span></span> <span data-ttu-id="bd240-111">Un'eccezione generata in un metodo che restituisce un <xref:System.Threading.Tasks.Task>o <xref:System.Threading.Tasks.Task%601>viene archiviato nell'attività restituita.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="bd240-111">An exception that’s raised in a method that returns a <xref:System.Threading.Tasks.Task> or  <xref:System.Threading.Tasks.Task%601> is stored in the returned task.</span></span> <span data-ttu-id="bd240-112">Se non si attende l'attività o si controllano in modo esplicito le eccezioni, l'eccezione viene persa.</span><span class="sxs-lookup"><span data-stu-id="bd240-112">If you don't await the task or explicitly check for exceptions, the exception is lost.</span></span> <span data-ttu-id="bd240-113">Se si attende l'attività, la relativa eccezione viene generata di nuovo.</span><span class="sxs-lookup"><span data-stu-id="bd240-113">If you await the task, its exception is rethrown.</span></span>  
  
 <span data-ttu-id="bd240-114">Come procedura consigliata, attendere sempre la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bd240-114">As a best practice, you should always await the call.</span></span>  
  
 <span data-ttu-id="bd240-115">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="bd240-115">By default, this message is a warning.</span></span> <span data-ttu-id="bd240-116">Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="bd240-116">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="bd240-117">**ID errore:** BC42358</span><span class="sxs-lookup"><span data-stu-id="bd240-117">**Error ID:** BC42358</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="bd240-118">Per risolvere questo avviso</span><span class="sxs-lookup"><span data-stu-id="bd240-118">To address this warning</span></span>  
  
-   <span data-ttu-id="bd240-119">Si consideri la possibilità di eliminare l'avviso solo se si è certi che non si desidera attendere il completamento della chiamata asincrona e che il metodo chiamato non generi alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="bd240-119">You should consider suppressing the warning only if you're sure that you don't want to wait for the asynchronous call to complete and that the called method won't raise any exceptions.</span></span> <span data-ttu-id="bd240-120">In tal caso, è possibile eliminare l'avviso assegnando il risultato dell'attività della chiamata a una variabile.</span><span class="sxs-lookup"><span data-stu-id="bd240-120">In that case, you can suppress the warning by assigning the task result of the call to a variable.</span></span>  
  
     <span data-ttu-id="bd240-121">Nell'esempio seguente viene illustrato come generare l'avviso, come eliminarlo e come attendere la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bd240-121">The following example shows how to cause the warning, how to suppress it, and how to await the call.</span></span>  
  
    ```vb  
    Async Function CallingMethodAsync() As Task  
  
        ResultsTextBox.Text &= vbCrLf & "  Entering calling method."  
  
        ' Variable delay is used to slow down the called method so that you  
        ' can distinguish between awaiting and not awaiting in the program's output.   
        ' You can adjust the value to produce the output that this topic shows   
        ' after the code.  
        Dim delay = 5000  
  
        ' Call #1.  
        ' Call an async method. Because you don't await it, its completion isn't   
        ' coordinated with the current method, CallingMethodAsync.  
        ' The following line causes the warning.  
        CalledMethodAsync(delay)  
  
        ' Call #2.  
        ' To suppress the warning without awaiting, you can assign the   
        ' returned task to a variable. The assignment doesn't change how  
        ' the program runs. However, the recommended practice is always to  
        ' await a call to an async method.  
        ' Replace Call #1 with the following line.  
        'Task delayTask = CalledMethodAsync(delay)  
  
        ' Call #3  
        ' To contrast with an awaited call, replace the unawaited call   
        ' (Call #1 or Call #2) with the following awaited call. The best   
        ' practice is to await the call.  
  
        'Await CalledMethodAsync(delay)  
  
        ' If the call to CalledMethodAsync isn't awaited, CallingMethodAsync  
        ' continues to run and, in this example, finishes its work and returns  
        ' to its caller.  
        ResultsTextBox.Text &= vbCrLf & "  Returning from calling method."  
    End Function  
  
    Async Function CalledMethodAsync(howLong As Integer) As Task  
  
        ResultsTextBox.Text &= vbCrLf & "    Entering called method, starting and awaiting Task.Delay."  
        ' Slow the process down a little so you can distinguish between awaiting  
        ' and not awaiting. Adjust the value for howLong if necessary.  
        Await Task.Delay(howLong)  
        ResultsTextBox.Text &= vbCrLf & "    Task.Delay is finished--returning from called method."  
    End Function  
    ```  
  
     <span data-ttu-id="bd240-122">Nell'esempio, se si sceglie Call #1 o Call #2, il metodo asincrono senza attesa (`CalledMethodAsync`) termina dopo che il relativo chiamante (`CallingMethodAsync`) e il chiamante del chiamante (`StartButton_Click`) sono completati.</span><span class="sxs-lookup"><span data-stu-id="bd240-122">In the example, if you choose Call #1 or Call #2, the unawaited async method (`CalledMethodAsync`) finishes after both its caller (`CallingMethodAsync`) and the caller's caller (`StartButton_Click`) are complete.</span></span> <span data-ttu-id="bd240-123">Nell'ultima riga nell'output seguente viene mostrato quando viene completato il metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="bd240-123">The last line in the following output shows you when the called method finishes.</span></span> <span data-ttu-id="bd240-124">L'entrata e l'uscita dal gestore eventi tramite cui viene chiamato `CallingMethodAsync` nell'esempio completo sono contrassegnate nell'output.</span><span class="sxs-lookup"><span data-stu-id="bd240-124">Entry to and exit from the event handler that calls `CallingMethodAsync` in the full example are marked in the output.</span></span>  
  
    ```  
    Entering the Click event handler.  
      Entering calling method.  
        Entering called method, starting and awaiting Task.Delay.  
      Returning from calling method.  
    Exiting the Click event handler.  
        Task.Delay is finished--returning from called method.  
    ```  
  
## <a name="example"></a><span data-ttu-id="bd240-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="bd240-125">Example</span></span>  
 <span data-ttu-id="bd240-126">Nell'applicazione Windows Presentation Foundation (WPF) seguente sono inclusi i metodi dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="bd240-126">The following Windows Presentation Foundation (WPF) application contains the methods from the previous example.</span></span> <span data-ttu-id="bd240-127">L'applicazione viene configurata con i passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="bd240-127">The following steps set up the application.</span></span>  
  
1.  <span data-ttu-id="bd240-128">Creare un'applicazione WPF e denominarla `AsyncWarning`.</span><span class="sxs-lookup"><span data-stu-id="bd240-128">Create a WPF application, and name it `AsyncWarning`.</span></span>  
  
2.  <span data-ttu-id="bd240-129">Nell'Editor di codice di Visual Studio scegliere la scheda **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="bd240-129">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="bd240-130">Se la scheda non è visibile, aprire il menu di scelta rapida per MainWindow.xaml in **Esplora soluzioni**, quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="bd240-130">If the tab isn't visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
3.  <span data-ttu-id="bd240-131">Sostituire il codice nella visualizzazione **XAML** di MainWindow.xaml con quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="bd240-131">Replace the code in the **XAML** view of MainWindow.xaml with the following code.</span></span>  
  
    ```vb  
    <Window x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="StartButton_Click" />  
            <TextBox x:Name="ResultsTextBox" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
        </Grid>  
    </Window>  
    ```  
  
     <span data-ttu-id="bd240-132">Una finestra semplice con un pulsante e una casella di testo viene visualizzata nella visualizzazione **Progettazione** di MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="bd240-132">A simple window that contains a button and a text box appears in the **Design** view of MainWindow.xaml.</span></span>  
  
     <span data-ttu-id="bd240-133">Per ulteriori informazioni sulla finestra di progettazione XAML, vedere [la creazione di un'interfaccia utente tramite XAML Designer](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="bd240-133">For more information about the XAML Designer, see [Creating a UI by using XAML Designer](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span> <span data-ttu-id="bd240-134">Per informazioni su come compilare una semplice interfaccia utente, vedere la "per creare un'applicazione WPF" e "per progettare una finestra principale semplice WPF" sezioni di [procedura dettagliata: accesso al Web tramite Async e Await](http://msdn.microsoft.com/library/25879a6d-fdee-4a38-bc98-bb8c24d16042).</span><span class="sxs-lookup"><span data-stu-id="bd240-134">For information about how to build your own simple UI, see the "To create a WPF application" and "To design a simple WPF MainWindow" sections of [Walkthrough: Accessing the Web by Using Async and Await](http://msdn.microsoft.com/library/25879a6d-fdee-4a38-bc98-bb8c24d16042).</span></span>  
  
4.  <span data-ttu-id="bd240-135">Sostituire il codice in MainWindow.xaml.vb con quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="bd240-135">Replace the code in MainWindow.xaml.vb with the following code.</span></span>  
  
    ```vb  
    Class MainWindow   
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
  
            ResultsTextBox.Text &= vbCrLf & "Entering the Click event handler."  
            Await CallingMethodAsync()  
            ResultsTextBox.Text &= vbCrLf & "Exiting the Click event handler."  
        End Sub  
  
        Async Function CallingMethodAsync() As Task  
  
            ResultsTextBox.Text &= vbCrLf & "  Entering calling method."  
  
            ' Variable delay is used to slow down the called method so that you  
            ' can distinguish between awaiting and not awaiting in the program's output.   
            ' You can adjust the value to produce the output that this topic shows   
            ' after the code.  
            Dim delay = 5000  
  
            ' Call #1.  
            ' Call an async method. Because you don't await it, its completion isn't   
            ' coordinated with the current method, CallingMethodAsync.  
            ' The following line causes the warning.  
            CalledMethodAsync(delay)  
  
            ' Call #2.  
            ' To suppress the warning without awaiting, you can assign the   
            ' returned task to a variable. The assignment doesn't change how  
            ' the program runs. However, the recommended practice is always to  
            ' await a call to an async method.  
  
            ' Replace Call #1 with the following line.  
            'Task delayTask = CalledMethodAsync(delay)  
  
            ' Call #3  
            ' To contrast with an awaited call, replace the unawaited call   
            ' (Call #1 or Call #2) with the following awaited call. The best   
            ' practice is to await the call.  
  
            'Await CalledMethodAsync(delay)  
  
            ' If the call to CalledMethodAsync isn't awaited, CallingMethodAsync  
            ' continues to run and, in this example, finishes its work and returns  
            ' to its caller.  
            ResultsTextBox.Text &= vbCrLf & "  Returning from calling method."  
        End Function  
  
        Async Function CalledMethodAsync(howLong As Integer) As Task  
  
            ResultsTextBox.Text &= vbCrLf & "    Entering called method, starting and awaiting Task.Delay."  
            ' Slow the process down a little so you can distinguish between awaiting  
            ' and not awaiting. Adjust the value for howLong if necessary.  
            Await Task.Delay(howLong)  
            ResultsTextBox.Text &= vbCrLf & "    Task.Delay is finished--returning from called method."  
        End Function  
  
    End Class  
  
    ' Output  
  
    ' Entering the Click event handler.  
    '   Entering calling method.  
    '     Entering called method, starting and awaiting Task.Delay.  
    '   Returning from calling method.  
    ' Exiting the Click event handler.  
    '     Task.Delay is finished--returning from called method.  
  
    ' Output  
  
    ' Entering the Click event handler.  
    '   Entering calling method.  
    '     Entering called method, starting and awaiting Task.Delay.  
    '     Task.Delay is finished--returning from called method.  
    '   Returning from calling method.  
    ' Exiting the Click event handler.  
    ```  
  
5.  <span data-ttu-id="bd240-136">Premere il tasto F5 per eseguire il programma e quindi scegliere il pulsante **Start** .</span><span class="sxs-lookup"><span data-stu-id="bd240-136">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="bd240-137">L'output previsto viene visualizzato alla fine del codice.</span><span class="sxs-lookup"><span data-stu-id="bd240-137">The expected output appears at the end of the code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd240-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd240-138">See Also</span></span>  
 <span data-ttu-id="bd240-139">[Await (operatore)](../../../visual-basic/language-reference/operators/await-operator.md) </span><span class="sxs-lookup"><span data-stu-id="bd240-139">[Await Operator](../../../visual-basic/language-reference/operators/await-operator.md) </span></span>  
<span data-ttu-id="bd240-140"> [Programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md)</span><span class="sxs-lookup"><span data-stu-id="bd240-140"> [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md)</span></span>

