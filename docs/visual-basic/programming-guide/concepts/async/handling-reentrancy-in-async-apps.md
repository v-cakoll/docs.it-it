---
title: Gestione della Reentrancy nelle applicazioni asincrone (Visual Basic)
ms.date: 07/20/2015
ms.assetid: ef3dc73d-13fb-4c5f-a686-6b84148bbffe
ms.openlocfilehash: 4b899a695fef0e626eb9db3d376a74acba17b086
ms.sourcegitcommit: 3540f614fc94f77ca4ab58df66db2d0f4d52dfee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2018
ms.locfileid: "34697157"
---
# <a name="handling-reentrancy-in-async-apps-visual-basic"></a><span data-ttu-id="abb48-102">Gestione della Reentrancy nelle applicazioni asincrone (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abb48-102">Handling Reentrancy in Async Apps (Visual Basic)</span></span>
<span data-ttu-id="abb48-103">Quando si include codice asincrono nell'applicazione, è consigliabile prevedere ed evitare la reentrancy, ovvero il reinserimento di un'operazione asincrona prima del suo completamento.</span><span class="sxs-lookup"><span data-stu-id="abb48-103">When you include asynchronous code in your app, you should consider and possibly prevent reentrancy, which refers to reentering an asynchronous operation before it has completed.</span></span> <span data-ttu-id="abb48-104">Se non vengono identificate e gestite le possibilità di reentrancy, esse possono causare risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="abb48-104">If you don't identify and handle possibilities for reentrancy, it can cause unexpected results.</span></span>  
  
 <span data-ttu-id="abb48-105">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="abb48-105">**In this topic**</span></span>  
  
-   [<span data-ttu-id="abb48-106">Riconoscimento della reentrancy</span><span class="sxs-lookup"><span data-stu-id="abb48-106">Recognizing Reentrancy</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
-   [<span data-ttu-id="abb48-107">Gestione della reentrancy</span><span class="sxs-lookup"><span data-stu-id="abb48-107">Handling Reentrancy</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
    -   [<span data-ttu-id="abb48-108">Disabilitare il pulsante Start</span><span class="sxs-lookup"><span data-stu-id="abb48-108">Disable the Start Button</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
    -   [<span data-ttu-id="abb48-109">Annullare e riavviare l'operazione</span><span class="sxs-lookup"><span data-stu-id="abb48-109">Cancel and Restart the Operation</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
    -   [<span data-ttu-id="abb48-110">Eseguire più operazioni e mettere in coda l'output</span><span class="sxs-lookup"><span data-stu-id="abb48-110">Run Multiple Operations and Queue the Output</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
-   [<span data-ttu-id="abb48-111">Revisione ed esecuzione dell'app di esempio</span><span class="sxs-lookup"><span data-stu-id="abb48-111">Reviewing and Running the Example App</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
> [!NOTE]
>  <span data-ttu-id="abb48-112">Per eseguire l'esempio, è necessario che nel computer siano installati Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="abb48-112">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <a name="BKMK_RecognizingReentrancy"></a> <span data-ttu-id="abb48-113">Riconoscimento della reentrancy</span><span class="sxs-lookup"><span data-stu-id="abb48-113">Recognizing Reentrancy</span></span>  
 <span data-ttu-id="abb48-114">Nell'esempio riportato in questo argomento viene scelto un pulsante **Start** per avviare un'app asincrona che scarica una serie di siti Web e calcola il numero totale di byte scaricati.</span><span class="sxs-lookup"><span data-stu-id="abb48-114">In the example in this topic, users choose a **Start** button to initiate an asynchronous app that downloads a series of websites and calculates the total number of bytes that are downloaded.</span></span> <span data-ttu-id="abb48-115">Una versione sincrona dell'esempio avrebbe risposto allo stesso modo indipendentemente dal numero di volte che un utente sceglie il pulsante perché, dopo la prima volta, il thread dell'interfaccia utente ignora tali eventi fino al termine dell'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="abb48-115">A synchronous version of the example would respond the same way regardless of how many times a user chooses the button because, after the first time, the UI thread ignores those events until the app finishes running.</span></span> <span data-ttu-id="abb48-116">In un'applicazione asincrona, tuttavia, il thread dell'interfaccia utente continua a rispondere e potrebbe essere possibile riattivare l'operazione asincrona prima del suo completamento.</span><span class="sxs-lookup"><span data-stu-id="abb48-116">In an asynchronous app, however, the UI thread continues to respond, and you might reenter the asynchronous operation before it has completed.</span></span>  
  
 <span data-ttu-id="abb48-117">Nell'esempio seguente viene illustrato l'output previsto se l'utente sceglie il pulsante **Start** una sola volta.</span><span class="sxs-lookup"><span data-stu-id="abb48-117">The following example shows the expected output if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="abb48-118">Viene visualizzato un elenco dei siti Web scaricati con la dimensione, espressa in byte, di ogni sito.</span><span class="sxs-lookup"><span data-stu-id="abb48-118">A list of the downloaded websites appears with the size, in bytes, of each site.</span></span> <span data-ttu-id="abb48-119">Il numero totale di byte viene visualizzato alla fine.</span><span class="sxs-lookup"><span data-stu-id="abb48-119">The total number of bytes appears at the end.</span></span>  
  
```  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
7. msdn.microsoft.com                                            42972  
8. msdn.microsoft.com/library/ff730837.aspx               146159  
  
TOTAL bytes returned:  890591  
```  
  
 <span data-ttu-id="abb48-120">Tuttavia, se l'utente sceglie il pulsante più volte, il gestore eventi viene chiamato più volte e il processo di download viene riattivato ogni volta.</span><span class="sxs-lookup"><span data-stu-id="abb48-120">However, if the user chooses the button more than once, the event handler is invoked repeatedly, and the download process is reentered each time.</span></span> <span data-ttu-id="abb48-121">Di conseguenza, diverse operazioni asincrone sono in esecuzione contemporaneamente, l'output si sovrappone ai risultati e il numero totale di byte è poco chiaro.</span><span class="sxs-lookup"><span data-stu-id="abb48-121">As a result, several asynchronous operations are running at the same time, the output interleaves the results, and the total number of bytes is confusing.</span></span>  
  
```  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
7. msdn.microsoft.com                                            42972  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
8. msdn.microsoft.com/library/ff730837.aspx               146159  
  
TOTAL bytes returned:  890591  
  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
7. msdn.microsoft.com                                            42972  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
8. msdn.microsoft.com/library/ff730837.aspx               146159  
  
TOTAL bytes returned:  890591  
  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
7. msdn.microsoft.com                                            42972  
8. msdn.microsoft.com/library/ff730837.aspx               146159  
  
TOTAL bytes returned:  890591  
```  
  
 <span data-ttu-id="abb48-122">È possibile esaminare il codice che genera l'output andando alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="abb48-122">You can review the code that produces this output by scrolling to the end of this topic.</span></span> <span data-ttu-id="abb48-123">È possibile provare il codice scaricando la soluzione nel computer locale ed eseguendo il progetto WebsiteDownload oppure usando il codice alla fine di questo argomento per creare un progetto personalizzato. Per altre informazioni e istruzioni, vedere [Revisione ed esecuzione dell'app di esempio](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645).</span><span class="sxs-lookup"><span data-stu-id="abb48-123">You can experiment with the code by downloading the solution to your local computer and then running the WebsiteDownload project or by using the code at the end of this topic to create your own project For more information and instructions, see [Reviewing and Running the Example App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645).</span></span>  
  
##  <a name="BKMK_HandlingReentrancy"></a> <span data-ttu-id="abb48-124">Gestione della reentrancy</span><span class="sxs-lookup"><span data-stu-id="abb48-124">Handling Reentrancy</span></span>  
 <span data-ttu-id="abb48-125">È possibile gestire la reentrancy in diversi modi, a seconda delle operazioni che si desidera che l'applicazione esegua.</span><span class="sxs-lookup"><span data-stu-id="abb48-125">You can handle reentrancy in a variety of ways, depending on what you want your app to do.</span></span> <span data-ttu-id="abb48-126">In questo argomento vengono illustrati gli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="abb48-126">This topic presents the following examples:</span></span>  
  
-   [<span data-ttu-id="abb48-127">Disabilitare il pulsante Start</span><span class="sxs-lookup"><span data-stu-id="abb48-127">Disable the Start Button</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
     <span data-ttu-id="abb48-128">Disabilitare il pulsante **Start** mentre l'operazione è in esecuzione in modo che l'utente non la interrompa.</span><span class="sxs-lookup"><span data-stu-id="abb48-128">Disable the **Start** button while the operation is running so that the user can't interrupt it.</span></span>  
  
-   [<span data-ttu-id="abb48-129">Annullare e riavviare l'operazione</span><span class="sxs-lookup"><span data-stu-id="abb48-129">Cancel and Restart the Operation</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
     <span data-ttu-id="abb48-130">Annullare le operazioni ancora in esecuzione quando l'utente sceglie di nuovo il pulsante **Start** e consentire la continuazione dell'operazione richiesta più di recente.</span><span class="sxs-lookup"><span data-stu-id="abb48-130">Cancel any operation that is still running when the user chooses the **Start** button again, and then let the most recently requested operation continue.</span></span>  
  
-   [<span data-ttu-id="abb48-131">Eseguire più operazioni e mettere in coda l'output</span><span class="sxs-lookup"><span data-stu-id="abb48-131">Run Multiple Operations and Queue the Output</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
     <span data-ttu-id="abb48-132">Consentire l'esecuzione asincrona di tutte le operazioni richieste, ma coordinare la visualizzazione dell'output in modo che vengano visualizzati i risultati di ogni operazione tutti insieme e ordinati.</span><span class="sxs-lookup"><span data-stu-id="abb48-132">Allow all requested operations to run asynchronously, but coordinate the display of output so that the results from each operation appear together and in order.</span></span>  
  
###  <a name="BKMK_DisableTheStartButton"></a> <span data-ttu-id="abb48-133">Disabilitare il pulsante Start</span><span class="sxs-lookup"><span data-stu-id="abb48-133">Disable the Start Button</span></span>  
 <span data-ttu-id="abb48-134">È possibile bloccare il pulsante **Start** durante l'esecuzione di un'operazione disabilitando il pulsante nella parte superiore del gestore eventi `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="abb48-134">You can block the **Start** button while an operation is running by disabling the button at the top of the `StartButton_Click` event handler.</span></span> <span data-ttu-id="abb48-135">È possibile riabilitare il pulsante dall'interno un blocco `Finally` al termine dell'operazione in modo che gli utenti possano eseguire nuovamente l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="abb48-135">You can then reenable the button from within a  `Finally` block when the operation finishes so that users can run the app again.</span></span>  
  
 <span data-ttu-id="abb48-136">Il codice seguente illustra queste modifiche, contrassegnate da asterischi.</span><span class="sxs-lookup"><span data-stu-id="abb48-136">The following code shows these changes, which are marked with asterisks.</span></span> <span data-ttu-id="abb48-137">È possibile aggiungere le modifiche al codice alla fine di questo argomento, oppure è possibile scaricare l'applicazione finita da [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Esempio di progetti asincroni: reentrancy in applicazioni desktop .NET).</span><span class="sxs-lookup"><span data-stu-id="abb48-137">You can add the changes to the code at the end of this topic, or you can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="abb48-138">Il nome del progetto è DisableStartButton.</span><span class="sxs-lookup"><span data-stu-id="abb48-138">The project name is DisableStartButton.</span></span>  
  
```vb  
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
    ' This line is commented out to make the results clearer in the output.  
    'ResultsTextBox.Text = ""  
  
    ' ***Disable the Start button until the downloads are complete.   
    StartButton.IsEnabled = False  
  
    Try  
        Await AccessTheWebAsync()  
  
    Catch ex As Exception  
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."  
    ' ***Enable the Start button in case you want to run the program again.   
    Finally  
        StartButton.IsEnabled = True  
  
    End Try  
End Sub  
```  
  
 <span data-ttu-id="abb48-139">In seguito alle modifiche, il pulsante non risponde mentre `AccessTheWebAsync` sta scaricando i siti Web. Pertanto, il processo non potrà essere riattivato.</span><span class="sxs-lookup"><span data-stu-id="abb48-139">As a result of the changes, the button doesn't respond while `AccessTheWebAsync` is downloading the websites, so the process can’t be reentered.</span></span>  
  
###  <a name="BKMK_CancelAndRestart"></a> <span data-ttu-id="abb48-140">Annullare e riavviare l'operazione</span><span class="sxs-lookup"><span data-stu-id="abb48-140">Cancel and Restart the Operation</span></span>  
 <span data-ttu-id="abb48-141">Anziché disabilitare il pulsante **Start**, è possibile tenere attivo il pulsante ma, se l'utente sceglie di nuovo il pulsante, è necessario annullare l'operazione in esecuzione e consentire la continuazione dell'operazione richiesta più di recente.</span><span class="sxs-lookup"><span data-stu-id="abb48-141">Instead of disabling the **Start** button, you can keep the button active but, if the user chooses that button again, cancel the operation that's already running and let the most recently started operation continue.</span></span>  
  
 <span data-ttu-id="abb48-142">Per ulteriori informazioni sull'annullamento, vedere [ottimizzazione Async applicazione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="abb48-142">For more information about cancellation, see [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md).</span></span>  
  
 <span data-ttu-id="abb48-143">Per configurare questo scenario, apportare le modifiche seguenti al codice di base fornito in [Revisione ed esecuzione dell'app di esempio](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645).</span><span class="sxs-lookup"><span data-stu-id="abb48-143">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645).</span></span> <span data-ttu-id="abb48-144">È anche possibile scaricare l'app finita da [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Esempio di progetti asincroni: reentrancy in applicazioni desktop .NET).</span><span class="sxs-lookup"><span data-stu-id="abb48-144">You also can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="abb48-145">Il nome di questo progetto è CancelAndRestart.</span><span class="sxs-lookup"><span data-stu-id="abb48-145">The name of this project is CancelAndRestart.</span></span>  
  
1.  <span data-ttu-id="abb48-146">Dichiarare una variabile <xref:System.Threading.CancellationTokenSource>, `cts`, che sia compresa nell'ambito per tutti i metodi.</span><span class="sxs-lookup"><span data-stu-id="abb48-146">Declare a <xref:System.Threading.CancellationTokenSource> variable, `cts`, that’s in scope for all methods.</span></span>  
  
    ```vb  
    Class MainWindow // Or Class MainPage  
  
        ' *** Declare a System.Threading.CancellationTokenSource.  
        Dim cts As CancellationTokenSource  
    ```  
  
2.  <span data-ttu-id="abb48-147">In `StartButton_Click` determinare se un'operazione è già in corso.</span><span class="sxs-lookup"><span data-stu-id="abb48-147">In `StartButton_Click`, determine whether an operation is already underway.</span></span> <span data-ttu-id="abb48-148">Se il valore di `cts` è `Nothing`, nessuna operazione è già attiva.</span><span class="sxs-lookup"><span data-stu-id="abb48-148">If the value of `cts` is `Nothing`, no operation is already active.</span></span> <span data-ttu-id="abb48-149">Se il valore non `Nothing`, viene annullata l'operazione che è già in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="abb48-149">If the value isn't `Nothing`, the operation that is already running is canceled.</span></span>  
  
    ```vb  
    ' *** If a download process is already underway, cancel it.  
    If cts IsNot Nothing Then  
        cts.Cancel()  
    End If  
    ```  
  
3.  <span data-ttu-id="abb48-150">Impostare `cts` su un valore diverso che rappresenti il processo corrente.</span><span class="sxs-lookup"><span data-stu-id="abb48-150">Set `cts` to a different value that represents the current process.</span></span>  
  
    ```vb  
    ' *** Now set cts to cancel the current process if the button is chosen again.  
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()  
    cts = newCTS  
    ```  
  
4.  <span data-ttu-id="abb48-151">Alla fine di `StartButton_Click`, il processo corrente è stato completato, quindi impostare il valore di `cts` al `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="abb48-151">At the end of `StartButton_Click`, the current process is complete, so set the value of `cts` back to `Nothing`.</span></span>  
  
    ```vb  
    ' *** When the process completes, signal that another process can proceed.  
    If cts Is newCTS Then  
        cts = Nothing  
    End If  
    ```  
  
 <span data-ttu-id="abb48-152">Il codice seguente illustra tutte le modifiche in `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="abb48-152">The following code shows all the changes in `StartButton_Click`.</span></span> <span data-ttu-id="abb48-153">Le aggiunte sono contrassegnate con asterischi.</span><span class="sxs-lookup"><span data-stu-id="abb48-153">The additions are marked with asterisks.</span></span>  
  
```vb  
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
  
    ' This line is commented out to make the results clearer.   
    'ResultsTextBox.Text = ""  
  
    ' *** If a download process is underway, cancel it.  
    If cts IsNot Nothing Then  
        cts.Cancel()  
    End If  
  
    ' *** Now set cts to cancel the current process if the button is chosen again.  
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()  
    cts = newCTS  
  
    Try  
        ' *** Send a token to carry the message if the operation is canceled.  
        Await AccessTheWebAsync(cts.Token)  
  
    Catch ex As OperationCanceledException  
        ResultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
    Catch ex As Exception  
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."  
    End Try  
  
    ' *** When the process is complete, signal that another process can proceed.  
    If cts Is newCTS Then  
        cts = Nothing  
    End If  
End Sub  
```  
  
 <span data-ttu-id="abb48-154">In `AccessTheWebAsync`, apportare le seguenti modifiche.</span><span class="sxs-lookup"><span data-stu-id="abb48-154">In `AccessTheWebAsync`, make the following changes.</span></span>  
  
-   <span data-ttu-id="abb48-155">Aggiungere un parametro per accettare il token di annullamento da `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="abb48-155">Add a parameter to accept the cancellation token from `StartButton_Click`.</span></span>  
  
-   <span data-ttu-id="abb48-156">Usare il metodo <xref:System.Net.Http.HttpClient.GetAsync%2A> per scaricare i siti Web, in quanto `GetAsync` accetta un argomento <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="abb48-156">Use the <xref:System.Net.Http.HttpClient.GetAsync%2A> method to download the websites because `GetAsync` accepts a <xref:System.Threading.CancellationToken> argument.</span></span>  
  
-   <span data-ttu-id="abb48-157">Prima di chiamare `DisplayResults` per visualizzare i risultati per ogni sito Web scaricato, controllare `ct` per verificare che l'operazione corrente non sia stata annullata.</span><span class="sxs-lookup"><span data-stu-id="abb48-157">Before calling `DisplayResults` to display the results for each downloaded website, check `ct` to verify that the current operation hasn’t been canceled.</span></span>  
  
 <span data-ttu-id="abb48-158">Il codice seguente illustra queste modifiche, contrassegnate da asterischi.</span><span class="sxs-lookup"><span data-stu-id="abb48-158">The following code shows these changes, which are marked with asterisks.</span></span>  
  
```vb  
' *** Provide a parameter for the CancellationToken from StartButton_Click.  
Private Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
  
    ' Declare an HttpClient object.  
    Dim client = New HttpClient()  
  
    ' Make a list of web addresses.  
    Dim urlList As List(Of String) = SetUpURLList()  
  
    Dim total = 0  
    Dim position = 0  
  
    For Each url In urlList  
        ' *** Use the HttpClient.GetAsync method because it accepts a   
        ' cancellation token.  
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ' *** Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ' *** Check for cancellations before displaying information about the   
        ' latest site.   
        ct.ThrowIfCancellationRequested()  
  
        position += 1  
        DisplayResults(url, urlContents, position)  
  
        ' Update the total.  
        total += urlContents.Length  
    Next  
  
    ' Display the total count for all of the websites.  
    ResultsTextBox.Text &=  
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)  
End Function  
```  
  
 <span data-ttu-id="abb48-159">Se si sceglie il pulsante **Start** più volte durante l'esecuzione di questa app, i risultati generati devono essere simili all'output seguente.</span><span class="sxs-lookup"><span data-stu-id="abb48-159">If you choose the **Start** button several times while this app is running, it should produce results that resemble the following output.</span></span>  
  
```  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               122505  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
Download canceled.  
  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
Download canceled.  
  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
7. msdn.microsoft.com                                            42972  
8. msdn.microsoft.com/library/ff730837.aspx               146159  
  
TOTAL bytes returned:  890591  
```  
  
 <span data-ttu-id="abb48-160">Per eliminare gli elenchi parziali, rimuovere la prima riga di codice in `StartButton_Click` per cancellare la casella di testo ogni volta che l'utente riavvia l'operazione.</span><span class="sxs-lookup"><span data-stu-id="abb48-160">To eliminate the partial lists, uncomment the first line of code in `StartButton_Click` to clear the text box each time the user restarts the operation.</span></span>  
  
###  <a name="BKMK_RunMultipleOperations"></a> <span data-ttu-id="abb48-161">Eseguire più operazioni e mettere in coda l'output</span><span class="sxs-lookup"><span data-stu-id="abb48-161">Run Multiple Operations and Queue the Output</span></span>  
 <span data-ttu-id="abb48-162">Il terzo esempio è il più complesso in quanto l'app avvia un'altra operazione asincrona ogni volta che l'utente sceglie il pulsante **Start** e tutte le operazioni vengono eseguite fino al completamento.</span><span class="sxs-lookup"><span data-stu-id="abb48-162">This third example is the most complicated in that the app starts another asynchronous operation each time that the user chooses the **Start** button, and all the operations run to completion.</span></span> <span data-ttu-id="abb48-163">Tutte le operazioni richieste scaricano i siti Web dall'elenco in modo asincrono, ma l'output delle operazioni viene visualizzato in sequenza.</span><span class="sxs-lookup"><span data-stu-id="abb48-163">All the requested operations download websites from the list asynchronously, but the output from the operations is presented sequentially.</span></span> <span data-ttu-id="abb48-164">In altre parole, l'attività di download effettiva è di tipo interleaved, come illustrato nell'output in [Riconoscimento della reentrancy](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), ma l'elenco dei risultati per ogni gruppo viene visualizzato separatamente.</span><span class="sxs-lookup"><span data-stu-id="abb48-164">That is, the actual downloading activity is interleaved, as the output in [Recognizing Reentrancy](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) shows, but the list of results for each group is presented separately.</span></span>  
  
 <span data-ttu-id="abb48-165">Le operazioni condividono un codice <xref:System.Threading.Tasks.Task> globale, `pendingWork`, che funge da gatekeeper per il processo di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="abb48-165">The operations share a global <xref:System.Threading.Tasks.Task>, `pendingWork`, which serves as a gatekeeper for the display process.</span></span>  
  
 <span data-ttu-id="abb48-166">È possibile eseguire questo esempio incollando le modifiche nel codice in [Compilazione dell'app](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) oppure è possibile attenersi alle istruzioni riportate in [Download dell'app](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) per scaricare l'esempio ed eseguire il progetto QueueResults.</span><span class="sxs-lookup"><span data-stu-id="abb48-166">You can run this example by pasting the changes into the code in [Building the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), or you can follow the instructions in [Downloading the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) to download the sample and then run the QueueResults project.</span></span>  
  
 <span data-ttu-id="abb48-167">Nell'output seguente viene illustrato il risultato restituito quando l'utente sceglie il pulsante **Start** una sola volta.</span><span class="sxs-lookup"><span data-stu-id="abb48-167">The following output shows the result if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="abb48-168">L'etichetta A indica che il risultato fa riferimento alla prima volta che il pulsante **Start** viene scelto.</span><span class="sxs-lookup"><span data-stu-id="abb48-168">The letter label, A, indicates that the result is from the first time the **Start** button is chosen.</span></span> <span data-ttu-id="abb48-169">I numeri indicano l'ordine degli URL nell'elenco delle destinazioni di download.</span><span class="sxs-lookup"><span data-stu-id="abb48-169">The numbers show the order of the URLs in the list of download targets.</span></span>  
  
```  
#Starting group A.  
#Task assigned for group A.  
  
A-1. msdn.microsoft.com/library/hh191443.aspx                87389  
A-2. msdn.microsoft.com/library/aa578028.aspx               209858  
A-3. msdn.microsoft.com/library/jj155761.aspx                30870  
A-4. msdn.microsoft.com/library/hh290140.aspx               119027  
A-5. msdn.microsoft.com/library/hh524395.aspx                71260  
A-6. msdn.microsoft.com/library/ms404677.aspx               199186  
A-7. msdn.microsoft.com                                            53266  
A-8. msdn.microsoft.com/library/ff730837.aspx               148020  
  
TOTAL bytes returned:  918876  
  
#Group A is complete.  
```  
  
 <span data-ttu-id="abb48-170">Se l'utente sceglie il pulsante **Start** tre volte, l'app genera un output simile alle righe seguenti.</span><span class="sxs-lookup"><span data-stu-id="abb48-170">If the user chooses the **Start** button three times, the app produces output that resembles the following lines.</span></span> <span data-ttu-id="abb48-171">Le righe di informazioni che iniziano con un cancelletto (#) tengono traccia dello stato di avanzamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="abb48-171">The information lines that start with a pound sign (#) trace the progress of the application.</span></span>  
  
```  
#Starting group A.  
#Task assigned for group A.  
  
A-1. msdn.microsoft.com/library/hh191443.aspx                87389  
A-2. msdn.microsoft.com/library/aa578028.aspx               207089  
A-3. msdn.microsoft.com/library/jj155761.aspx                30870  
A-4. msdn.microsoft.com/library/hh290140.aspx               119027  
A-5. msdn.microsoft.com/library/hh524395.aspx                71259  
A-6. msdn.microsoft.com/library/ms404677.aspx               199185  
  
#Starting group B.  
#Task assigned for group B.  
  
A-7. msdn.microsoft.com                                            53266  
  
#Starting group C.  
#Task assigned for group C.  
  
A-8. msdn.microsoft.com/library/ff730837.aspx               148010  
  
TOTAL bytes returned:  916095  
  
B-1. msdn.microsoft.com/library/hh191443.aspx                87389  
B-2. msdn.microsoft.com/library/aa578028.aspx               207089  
B-3. msdn.microsoft.com/library/jj155761.aspx                30870  
B-4. msdn.microsoft.com/library/hh290140.aspx               119027  
B-5. msdn.microsoft.com/library/hh524395.aspx                71260  
B-6. msdn.microsoft.com/library/ms404677.aspx               199186  
  
#Group A is complete.  
  
B-7. msdn.microsoft.com                                            53266  
B-8. msdn.microsoft.com/library/ff730837.aspx               148010  
  
TOTAL bytes returned:  916097  
  
C-1. msdn.microsoft.com/library/hh191443.aspx                87389  
C-2. msdn.microsoft.com/library/aa578028.aspx               207089  
  
#Group B is complete.  
  
C-3. msdn.microsoft.com/library/jj155761.aspx                30870  
C-4. msdn.microsoft.com/library/hh290140.aspx               119027  
C-5. msdn.microsoft.com/library/hh524395.aspx                72765  
C-6. msdn.microsoft.com/library/ms404677.aspx               199186  
C-7. msdn.microsoft.com                                            56190  
C-8. msdn.microsoft.com/library/ff730837.aspx               148010  
  
TOTAL bytes returned:  920526  
  
#Group C is complete.  
```  
  
 <span data-ttu-id="abb48-172">I gruppi B e C vengono avviati prima del completamento del gruppo A, ma l'output per ogni gruppo viene visualizzato separatamente.</span><span class="sxs-lookup"><span data-stu-id="abb48-172">Groups B and C start before group A has finished, but the output for the each group appears separately.</span></span> <span data-ttu-id="abb48-173">Viene prima visualizzato l'intero output del gruppo A, seguito dall'intero output del gruppo B e dall'intero output del gruppo C. L'app visualizza sempre i gruppi nell'ordine e, per ogni gruppo, visualizza sempre le informazioni sui singoli siti Web in base all'ordine in cui i relativi URL sono visualizzati nell'elenco di URL.</span><span class="sxs-lookup"><span data-stu-id="abb48-173">All the output for group A appears first, followed by all the output for group B, and then all the output for group C. The app always displays the groups in order and, for each group, always displays the information about the individual websites in the order that the URLs appear in the list of URLs.</span></span>  
  
 <span data-ttu-id="abb48-174">Tuttavia, è possibile prevedere l'ordine in cui vengono eseguiti i download.</span><span class="sxs-lookup"><span data-stu-id="abb48-174">However, you can't predict the order in which the downloads actually happen.</span></span> <span data-ttu-id="abb48-175">Dopo l'avvio di più gruppi, tutte le attività di download generate sono attive.</span><span class="sxs-lookup"><span data-stu-id="abb48-175">After multiple groups have been started, the download tasks that they generate are all active.</span></span> <span data-ttu-id="abb48-176">Non è possibile presupporre che A-1 venga scaricato prima di B-1 e che A-1 venga scaricato prima A 2.</span><span class="sxs-lookup"><span data-stu-id="abb48-176">You can't assume that A-1 will be downloaded before B-1, and you can't assume that A-1 will be downloaded before A-2.</span></span>  
  
#### <a name="global-definitions"></a><span data-ttu-id="abb48-177">Definizioni globali</span><span class="sxs-lookup"><span data-stu-id="abb48-177">Global Definitions</span></span>  
 <span data-ttu-id="abb48-178">Il codice di esempio contiene le seguenti dichiarazioni globali visibili da tutti i metodi.</span><span class="sxs-lookup"><span data-stu-id="abb48-178">The sample code contains the following two global declarations that are visible from all methods.</span></span>  
  
```vb  
Class MainWindow    ' Class MainPage in Windows Store app.  
  
    ' ***Declare the following variables where all methods can access them.   
    Private pendingWork As Task = Nothing  
    Private group As Char = ChrW(AscW("A") - 1)  
```  
  
 <span data-ttu-id="abb48-179">La variabile `Task`, `pendingWork`, controlla il processo di visualizzazione e impedisce a qualsiasi gruppo di interrompere l'operazione di visualizzazione di un altro gruppo.</span><span class="sxs-lookup"><span data-stu-id="abb48-179">The `Task` variable, `pendingWork`, oversees the display process and prevents any group from interrupting another group's display operation.</span></span> <span data-ttu-id="abb48-180">La variabile di tipo carattere, `group`, etichetta l'output dei vari gruppi per far sì che i risultati vengano visualizzati nell'ordine previsto.</span><span class="sxs-lookup"><span data-stu-id="abb48-180">The character variable, `group`, labels the output from different groups to verify that results appear in the expected order.</span></span>  
  
#### <a name="the-click-event-handler"></a><span data-ttu-id="abb48-181">Il gestore eventi Click</span><span class="sxs-lookup"><span data-stu-id="abb48-181">The Click Event Handler</span></span>  
 <span data-ttu-id="abb48-182">Il gestore eventi `StartButton_Click` incrementa la lettera del gruppo ogni volta che l'utente sceglie il pulsante **Start**.</span><span class="sxs-lookup"><span data-stu-id="abb48-182">The event handler, `StartButton_Click`, increments the group letter each time the user chooses the **Start** button.</span></span> <span data-ttu-id="abb48-183">Il gestore chiama quindi `AccessTheWebAsync` per eseguire l'operazione di download.</span><span class="sxs-lookup"><span data-stu-id="abb48-183">Then the handler calls `AccessTheWebAsync` to run the downloading operation.</span></span>  
  
```vb  
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
    ' ***Verify that each group's results are displayed together, and that  
    ' the groups display in order, by marking each group with a letter.  
    group = ChrW(AscW(group) + 1)  
    ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Starting group {0}.", group)  
  
    Try  
        ' *** Pass the group value to AccessTheWebAsync.  
        Dim finishedGroup As Char = Await AccessTheWebAsync(group)  
  
        ' The following line verifies a successful return from the download and   
        ' display procedures.   
        ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Group {0} is complete." & vbCrLf, finishedGroup)  
  
    Catch ex As Exception  
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."  
  
    End Try  
End Sub  
```  
  
#### <a name="the-accessthewebasync-method"></a><span data-ttu-id="abb48-184">Il metodo AccessTheWebAsync</span><span class="sxs-lookup"><span data-stu-id="abb48-184">The AccessTheWebAsync Method</span></span>  
 <span data-ttu-id="abb48-185">Questo esempio suddivide `AccessTheWebAsync` in due metodi.</span><span class="sxs-lookup"><span data-stu-id="abb48-185">This example splits `AccessTheWebAsync` into two methods.</span></span> <span data-ttu-id="abb48-186">Il primo metodo, `AccessTheWebAsync`, avvia tutte le attività di download per un gruppo e configura `pendingWork` per il controllo del processo di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="abb48-186">The first method, `AccessTheWebAsync`, starts all the download tasks for a group and sets up `pendingWork` to control the display process.</span></span> <span data-ttu-id="abb48-187">Il metodo usa una query LINQ (Language Integrated Query) e <xref:System.Linq.Enumerable.ToArray%2A> per avviare tutte le attività di download contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="abb48-187">The method uses a Language Integrated Query (LINQ query) and <xref:System.Linq.Enumerable.ToArray%2A> to start all the download tasks at the same time.</span></span>  
  
 <span data-ttu-id="abb48-188">`AccessTheWebAsync` quindi chiama `FinishOneGroupAsync` per attendere il completamento di ogni download e visualizzare la relativa lunghezza.</span><span class="sxs-lookup"><span data-stu-id="abb48-188">`AccessTheWebAsync` then calls `FinishOneGroupAsync` to await the completion of each download and display its length.</span></span>  
  
 <span data-ttu-id="abb48-189">`FinishOneGroupAsync` restituisce un'attività assegnata a `pendingWork` in `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="abb48-189">`FinishOneGroupAsync` returns a task that's assigned to `pendingWork` in `AccessTheWebAsync`.</span></span> <span data-ttu-id="abb48-190">Tale valore impedisce l'interruzione da parte di un'altra operazione prima del completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="abb48-190">That value prevents interruption by another operation before the task is complete.</span></span>  
  
```vb  
Private Async Function AccessTheWebAsync(grp As Char) As Task(Of Char)  
  
    Dim client = New HttpClient()  
  
    ' Make a list of the web addresses to download.  
    Dim urlList As List(Of String) = SetUpURLList()  
  
    ' ***Kick off the downloads. The application of ToArray activates all the download tasks.  
    Dim getContentTasks As Task(Of Byte())() =  
        urlList.Select(Function(addr) client.GetByteArrayAsync(addr)).ToArray()  
  
    ' ***Call the method that awaits the downloads and displays the results.  
    ' Assign the Task that FinishOneGroupAsync returns to the gatekeeper task, pendingWork.  
    pendingWork = FinishOneGroupAsync(urlList, getContentTasks, grp)  
  
    ResultsTextBox.Text &=  
        String.Format(vbCrLf & "#Task assigned for group {0}. Download tasks are active." & vbCrLf, grp)  
  
    ' ***This task is complete when a group has finished downloading and displaying.  
    Await pendingWork  
  
    ' You can do other work here or just return.  
    Return grp  
End Function  
```  
  
#### <a name="the-finishonegroupasync-method"></a><span data-ttu-id="abb48-191">Il metodo FinishOneGroupAsync</span><span class="sxs-lookup"><span data-stu-id="abb48-191">The FinishOneGroupAsync Method</span></span>  
 <span data-ttu-id="abb48-192">Questo metodo consente di scorrere le attività di download in reciproca attesa in un gruppo, nonché visualizza la lunghezza del sito Web scaricato e aggiunge la lunghezza al totale.</span><span class="sxs-lookup"><span data-stu-id="abb48-192">This method cycles through the download tasks in a group, awaiting each one, displaying the length of the downloaded website, and adding the length to the total.</span></span>  
  
 <span data-ttu-id="abb48-193">La prima istruzione in `FinishOneGroupAsync` usa `pendingWork` per assicurarsi che l'uso del metodo non interferisca con un'operazione già presente nel processo di visualizzazione o in attesa.</span><span class="sxs-lookup"><span data-stu-id="abb48-193">The first statement in `FinishOneGroupAsync` uses `pendingWork` to make sure that entering the method doesn't interfere with an operation that is already in the display process or that's already waiting.</span></span> <span data-ttu-id="abb48-194">Se tale operazione è in corso, l'operazione di attivazione deve attendere il suo turno.</span><span class="sxs-lookup"><span data-stu-id="abb48-194">If such an operation is in progress, the entering operation must wait its turn.</span></span>  
  
```vb  
Private Async Function FinishOneGroupAsync(urls As List(Of String), contentTasks As Task(Of Byte())(), grp As Char) As Task  
  
    ' Wait for the previous group to finish displaying results.  
    If pendingWork IsNot Nothing Then  
        Await pendingWork  
    End If  
  
    Dim total = 0  
  
    ' contentTasks is the array of Tasks that was created in AccessTheWebAsync.  
    For i As Integer = 0 To contentTasks.Length - 1  
        ' Await the download of a particular URL, and then display the URL and  
        ' its length.  
        Dim content As Byte() = Await contentTasks(i)  
        DisplayResults(urls(i), content, i, grp)  
        total += content.Length  
    Next  
  
    ' Display the total count for all of the websites.  
    ResultsTextBox.Text &=  
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)  
End Function  
```  
  
 <span data-ttu-id="abb48-195">È possibile eseguire questo esempio incollando le modifiche nel codice in [Compilazione dell'app](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) oppure è possibile attenersi alle istruzioni riportate in [Download dell'app](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) per scaricare l'esempio ed eseguire il progetto QueueResults.</span><span class="sxs-lookup"><span data-stu-id="abb48-195">You can run this example by pasting the changes into the code in [Building the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), or you can follow the instructions in [Downloading the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) to download the sample, and then run the QueueResults project.</span></span>  
  
#### <a name="points-of-interest"></a><span data-ttu-id="abb48-196">Punti di interesse</span><span class="sxs-lookup"><span data-stu-id="abb48-196">Points of Interest</span></span>  
 <span data-ttu-id="abb48-197">Le righe di informazioni che iniziano con un segno di cancelletto (#) nell'output descrivono il funzionamento dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="abb48-197">The information lines that start with a pound sign (#) in the output clarify how this example works.</span></span>  
  
 <span data-ttu-id="abb48-198">L'output mostra i modelli seguenti.</span><span class="sxs-lookup"><span data-stu-id="abb48-198">The output shows the following patterns.</span></span>  
  
-   <span data-ttu-id="abb48-199">Un gruppo può essere avviato anche se un gruppo precedente è visualizzato nel relativo output, ma la visualizzazione dell'output del gruppo precedente non viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="abb48-199">A group can be started while a previous group is displaying its output, but the display of the previous group's output isn't interrupted.</span></span>  
  
    ```  
    #Starting group A.  
    #Task assigned for group A. Download tasks are active.  
  
    A-1. msdn.microsoft.com/library/hh191443.aspx                87389  
    A-2. msdn.microsoft.com/library/aa578028.aspx               207089  
    A-3. msdn.microsoft.com/library/jj155761.aspx                30870  
    A-4. msdn.microsoft.com/library/hh290140.aspx               119037  
    A-5. msdn.microsoft.com/library/hh524395.aspx                71260  
  
    #Starting group B.  
    #Task assigned for group B. Download tasks are active.  
  
    A-6. msdn.microsoft.com/library/ms404677.aspx               199186  
    A-7. msdn.microsoft.com                                            53078  
    A-8. msdn.microsoft.com/library/ff730837.aspx               148010  
  
    TOTAL bytes returned:  915919  
  
    B-1. msdn.microsoft.com/library/hh191443.aspx                87388  
    B-2. msdn.microsoft.com/library/aa578028.aspx               207089  
    B-3. msdn.microsoft.com/library/jj155761.aspx                30870  
  
    #Group A is complete.  
  
    B-4. msdn.microsoft.com/library/hh290140.aspx               119027  
    B-5. msdn.microsoft.com/library/hh524395.aspx                71260  
    B-6. msdn.microsoft.com/library/ms404677.aspx               199186  
    B-7. msdn.microsoft.com                                            53078  
    B-8. msdn.microsoft.com/library/ff730837.aspx               148010  
  
    TOTAL bytes returned:  915908  
    ```  
  
-   <span data-ttu-id="abb48-200">Il `pendingWork` attività `Nothing` all'inizio di `FinishOneGroupAsync` solo per il gruppo, che viene avviato per primo.</span><span class="sxs-lookup"><span data-stu-id="abb48-200">The `pendingWork` task is `Nothing` at the start of `FinishOneGroupAsync` only for group A, which started first.</span></span> <span data-ttu-id="abb48-201">Il gruppo A non ha ancora completato un'espressione await quando raggiunge `FinishOneGroupAsync`.</span><span class="sxs-lookup"><span data-stu-id="abb48-201">Group A hasn’t yet completed an await expression when it reaches `FinishOneGroupAsync`.</span></span> <span data-ttu-id="abb48-202">Pertanto, il controllo non è stato restituito a `AccessTheWebAsync` e non è stata eseguita la prima assegnazione a `pendingWork`.</span><span class="sxs-lookup"><span data-stu-id="abb48-202">Therefore, control hasn't returned to `AccessTheWebAsync`, and the first assignment to `pendingWork` hasn't occurred.</span></span>  
  
-   <span data-ttu-id="abb48-203">Le due righe seguenti sono sempre visualizzate insieme nell'output.</span><span class="sxs-lookup"><span data-stu-id="abb48-203">The following two lines always appear together in the output.</span></span> <span data-ttu-id="abb48-204">Il codice non viene mai interrotto tra l'avvio dell'operazione di un gruppo in `StartButton_Click` e l'assegnazione di un'attività per il gruppo a `pendingWork`.</span><span class="sxs-lookup"><span data-stu-id="abb48-204">The code is never interrupted between starting a group's operation in `StartButton_Click` and assigning a task for the group to `pendingWork`.</span></span>  
  
    ```  
    #Starting group B.  
    #Task assigned for group B. Download tasks are active.  
    ```  
  
     <span data-ttu-id="abb48-205">Dopo che un gruppo entra in `StartButton_Click`, l'operazione non completa un'espressione await fino a quando l'operazione non entra in `FinishOneGroupAsync`.</span><span class="sxs-lookup"><span data-stu-id="abb48-205">After a group enters `StartButton_Click`, the operation doesn't complete an await expression until the operation enters `FinishOneGroupAsync`.</span></span> <span data-ttu-id="abb48-206">Pertanto, nessuna operazione può assumere il controllo durante l'esecuzione di tale segmento di codice.</span><span class="sxs-lookup"><span data-stu-id="abb48-206">Therefore, no other operation can gain control during that segment of code.</span></span>  
  
##  <a name="BKMD_SettingUpTheExample"></a> <span data-ttu-id="abb48-207">Revisione ed esecuzione dell'app di esempio</span><span class="sxs-lookup"><span data-stu-id="abb48-207">Reviewing and Running the Example App</span></span>  
 <span data-ttu-id="abb48-208">Per comprendere meglio l'applicazione di esempio, è possibile scaricarla, compilarla manualmente o esaminare il codice alla fine di questo argomento senza implementare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="abb48-208">To better understand the example app, you can download it, build it yourself, or review the code at the end of this topic without implementing the app.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abb48-209">Per eseguire l'esempio come applicazione dektop WPF (Windows Presentation Foundation), è necessario che nel computer siano installati Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="abb48-209">To run the example as a Windows Presentation Foundation (WPF) desktop app, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
###  <a name="BKMK_DownloadingTheApp"></a> <span data-ttu-id="abb48-210">Download dell'app</span><span class="sxs-lookup"><span data-stu-id="abb48-210">Downloading the App</span></span>  
  
1.  <span data-ttu-id="abb48-211">Scaricare il file compresso da [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Esempio di progetti asincroni: reentrancy in applicazioni desktop .NET).</span><span class="sxs-lookup"><span data-stu-id="abb48-211">Download the compressed file from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span>  
  
2.  <span data-ttu-id="abb48-212">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="abb48-212">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
3.  <span data-ttu-id="abb48-213">Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="abb48-213">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
4.  <span data-ttu-id="abb48-214">Passare alla cartella che contiene il codice di esempio decompresso e quindi aprire il file di soluzione (sln).</span><span class="sxs-lookup"><span data-stu-id="abb48-214">Navigate to the folder that holds the decompressed sample code, and then open the solution (.sln) file.</span></span>  
  
5.  <span data-ttu-id="abb48-215">In **Esplora soluzioni** aprire il menu di scelta rapida del progetto che si vuole eseguire e scegliere **Set as StartUpProject** (Imposta come progetto di avvio).</span><span class="sxs-lookup"><span data-stu-id="abb48-215">In **Solution Explorer**, open the shortcut menu for the project that you want to run, and then choose **Set as StartUpProject**.</span></span>  
  
6.  <span data-ttu-id="abb48-216">Premere CTRL+F5 per compilare ed eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="abb48-216">Choose the CTRL+F5 keys to build and run the project.</span></span>  
  
###  <a name="BKMK_BuildingTheApp"></a> <span data-ttu-id="abb48-217">Compilazione dell'app</span><span class="sxs-lookup"><span data-stu-id="abb48-217">Building the App</span></span>  
 <span data-ttu-id="abb48-218">Nella sezione seguente viene illustrato il codice per compilare l'esempio come app WPF.</span><span class="sxs-lookup"><span data-stu-id="abb48-218">The following section provides the code to build the example as a WPF app.</span></span>  
  
##### <a name="to-build-a-wpf-app"></a><span data-ttu-id="abb48-219">Per compilare un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="abb48-219">To build a WPF app</span></span>  
  
1.  <span data-ttu-id="abb48-220">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="abb48-220">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="abb48-221">Nella barra dei menu scegliere **File**, **Nuovo**, **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="abb48-221">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="abb48-222">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="abb48-222">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="abb48-223">Nel **modelli installati** riquadro espandere **Visual Basic**, quindi espandere **Windows**.</span><span class="sxs-lookup"><span data-stu-id="abb48-223">In the **Installed Templates** pane, expand **Visual Basic**, and then expand **Windows**.</span></span>  
  
4.  <span data-ttu-id="abb48-224">Dall'elenco dei tipi di progetto scegliere **Applicazione WPF**.</span><span class="sxs-lookup"><span data-stu-id="abb48-224">In the list of project types, choose **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="abb48-225">Assegnare al progetto il nome `WebsiteDownloadWPF` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="abb48-225">Name the project `WebsiteDownloadWPF`, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="abb48-226">Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="abb48-226">The new project appears in **Solution Explorer**.</span></span>  
  
6.  <span data-ttu-id="abb48-227">Nell'Editor di codice di Visual Studio scegliere la scheda **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="abb48-227">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="abb48-228">Se la scheda non è visibile, aprire il menu di scelta rapida per MainWindow.xaml in **Esplora soluzioni** e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="abb48-228">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
7.  <span data-ttu-id="abb48-229">Nella visualizzazione **XAML** di MainWindow.xaml sostituire il codice con quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="abb48-229">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>  
  
    ```vb  
    <Window x:Class="MainWindow"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:local="using:WebsiteDownloadWPF"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
        mc:Ignorable="d">  
  
        <Grid Width="517" Height="360">  
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="-1,0,0,0" VerticalAlignment="Top" Click="StartButton_Click" Height="53" Background="#FFA89B9B" FontSize="36" Width="518"  />  
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" Margin="-1,53,0,-36" TextWrapping="Wrap" VerticalAlignment="Top" Height="343" FontSize="10" ScrollViewer.VerticalScrollBarVisibility="Visible" Width="518" FontFamily="Lucida Console" />  
        </Grid>  
    </Window>  
    ```  
  
     <span data-ttu-id="abb48-230">Nella visualizzazione **Progettazione** di MainWindow.xaml viene visualizzata una finestra semplice contenente una casella di testo e un pulsante.</span><span class="sxs-lookup"><span data-stu-id="abb48-230">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>  
  
8.  <span data-ttu-id="abb48-231">Aggiunge un riferimento a <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="abb48-231">Add a reference for <xref:System.Net.Http>.</span></span>  
  
9. <span data-ttu-id="abb48-232">In **Esplora**, aprire il menu di scelta rapida per file e quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="abb48-232">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
10. <span data-ttu-id="abb48-233">In VB, sostituire il codice con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="abb48-233">In MainWindow.xaml.vb , replace the code with the following code.</span></span>  
  
    ```vb  
    ' Add the following Imports statements, and add a reference for System.Net.Http.  
    Imports System.Net.Http  
    Imports System.Threading  
  
    Class MainWindow  
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
            ' This line is commented out to make the results clearer in the output.  
            'ResultsTextBox.Text = ""  
  
            Try  
                Await AccessTheWebAsync()  
  
            Catch ex As Exception  
                ResultsTextBox.Text &= vbCrLf & "Downloads failed."  
  
            End Try  
        End Sub  
  
        Private Async Function AccessTheWebAsync() As Task  
  
            ' Declare an HttpClient object.  
            Dim client = New HttpClient()  
  
            ' Make a list of web addresses.  
            Dim urlList As List(Of String) = SetUpURLList()  
  
            Dim total = 0  
            Dim position = 0  
  
            For Each url In urlList  
                ' GetByteArrayAsync returns a task. At completion, the task  
                ' produces a byte array.  
                Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
  
                position += 1  
                DisplayResults(url, urlContents, position)  
  
                ' Update the total.  
                total += urlContents.Length  
            Next  
  
            ' Display the total count for all of the websites.  
            ResultsTextBox.Text &=  
                String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)  
        End Function  
  
        Private Function SetUpURLList() As List(Of String)  
            Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com/library/hh191443.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/jj155761.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/hh524395.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
            Return urls  
        End Function  
  
        Private Sub DisplayResults(url As String, content As Byte(), pos As Integer)  
            ' Display the length of each website. The string format is designed  
            ' to be used with a monospaced font, such as Lucida Console or  
            ' Global Monospace.  
  
            ' Strip off the "http:'".  
            Dim displayURL = url.Replace("http://", "")  
            ' Display position in the URL list, the URL, and the number of bytes.  
            ResultsTextBox.Text &= String.Format(vbCrLf & "{0}. {1,-58} {2,8}", pos, displayURL, content.Length)  
        End Sub  
    End Class  
    ```  
  
11. <span data-ttu-id="abb48-234">Premere CTRL+F5 per eseguire il programma e scegliere il pulsante **Start** più volte.</span><span class="sxs-lookup"><span data-stu-id="abb48-234">Choose the CTRL+F5 keys to run the program, and then choose the **Start** button several times.</span></span>  
  
12. <span data-ttu-id="abb48-235">Apportare le modifiche descritte in [Disabilitare il pulsante Start](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), [Annullare e riavviare l'operazione](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) o [Eseguire più operazioni e mettere in coda l'output](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) per gestire la reentrancy.</span><span class="sxs-lookup"><span data-stu-id="abb48-235">Make the changes from [Disable the Start Button](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), [Cancel and Restart the Operation](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), or [Run Multiple Operations and Queue the Output](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) to handle the reentrancy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abb48-236">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abb48-236">See Also</span></span>  
 [<span data-ttu-id="abb48-237">Procedura dettagliata: Accesso al Web con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abb48-237">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 [<span data-ttu-id="abb48-238">Programmazione asincrona con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abb48-238">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
