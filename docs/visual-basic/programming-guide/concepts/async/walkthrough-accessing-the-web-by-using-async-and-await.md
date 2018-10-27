---
title: 'Procedura dettagliata: accesso al Web con Async e Await (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
ms.openlocfilehash: 8998ed715306402f4d8cc98be82cbb8e4aac3f8e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194163"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a><span data-ttu-id="a2c6c-102">Procedura dettagliata: accesso al Web con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2c6c-102">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>
<span data-ttu-id="a2c6c-103">È possibile scrivere programmi asincroni in modo più semplice e intuitivo usando le funzionalità async/await.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-103">You can write asynchronous programs more easily and intuitively by using async/await features.</span></span> <span data-ttu-id="a2c6c-104">È possibile scrivere codice asincrono simile al codice sincrono e consentire al compilatore di gestire le complesse funzioni di callback e continuazione tipiche del codice asincrono.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>  
  
 <span data-ttu-id="a2c6c-105">Per altre informazioni sulla funzionalità Async, vedere [programmazione asincrona con Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="a2c6c-105">For more information about the Async feature, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="a2c6c-106">Questa procedura dettagliata inizia con l'esecuzione di un'applicazione Windows Presentation Foundation (WPF) sincrona che somma il numero di byte in un elenco di siti Web.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="a2c6c-107">La procedura dettagliata converte quindi l'applicazione in una soluzione asincrona usando le nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>  
  
 <span data-ttu-id="a2c6c-108">Se non si desidera compilare manualmente le applicazioni, è possibile scaricare "Esempio asincrono: accesso alla procedura dettagliata Web (C# e Visual Basic)" da [esempi di codice per sviluppatori](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span><span class="sxs-lookup"><span data-stu-id="a2c6c-108">If you don't want to build the applications yourself, you can download "Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)" from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>  
  
 <span data-ttu-id="a2c6c-109">Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2c6c-109">In this walkthrough, you complete the following tasks:</span></span>  
  
-   [<span data-ttu-id="a2c6c-110">Per creare un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="a2c6c-110">To create a WPF application</span></span>](#CreateWPFApp)  
  
-   [<span data-ttu-id="a2c6c-111">Per progettare una finestra WPF MainWindow semplice</span><span class="sxs-lookup"><span data-stu-id="a2c6c-111">To design a simple WPF MainWindow</span></span>](#MainWindow)  
  
-   [<span data-ttu-id="a2c6c-112">Per aggiungere un riferimento</span><span class="sxs-lookup"><span data-stu-id="a2c6c-112">To add a reference</span></span>](#AddRef)  
  
-   [<span data-ttu-id="a2c6c-113">Per aggiungere istruzioni Imports necessarie</span><span class="sxs-lookup"><span data-stu-id="a2c6c-113">To add necessary Imports statements</span></span>](#ImportsState)  
  
-   [<span data-ttu-id="a2c6c-114">Per creare un'applicazione sincrona</span><span class="sxs-lookup"><span data-stu-id="a2c6c-114">To create a synchronous application</span></span>](#synchronous)  
  
-   [<span data-ttu-id="a2c6c-115">Per eseguire il test della soluzione sincrona</span><span class="sxs-lookup"><span data-stu-id="a2c6c-115">To test the synchronous solution</span></span>](#testSynch)  
  
-   [<span data-ttu-id="a2c6c-116">Per convertire GetURLContents in un metodo asincrono</span><span class="sxs-lookup"><span data-stu-id="a2c6c-116">To convert GetURLContents to an asynchronous method</span></span>](#GetURLContents)  
  
-   [<span data-ttu-id="a2c6c-117">Per Convertire SumPageSizes in un metodo asincrono</span><span class="sxs-lookup"><span data-stu-id="a2c6c-117">To convert SumPageSizes to an asynchronous method</span></span>](#SumPageSizes)  
  
-   [<span data-ttu-id="a2c6c-118">Per convertire startButton_Click in un metodo asincrono</span><span class="sxs-lookup"><span data-stu-id="a2c6c-118">To convert startButton_Click to an asynchronous method</span></span>](#startButton)  
  
-   [<span data-ttu-id="a2c6c-119">Per eseguire il test della soluzione asincrona</span><span class="sxs-lookup"><span data-stu-id="a2c6c-119">To test the asynchronous solution</span></span>](#testAsynch)  
  
-   [<span data-ttu-id="a2c6c-120">Per sostituire GetURLContentsAsync con un metodo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a2c6c-120">To replace method GetURLContentsAsync with a .NET Framework method</span></span>](#GetURLContentsAsync)  
  
-   [<span data-ttu-id="a2c6c-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2c6c-121">Example</span></span>](#BKMK_CompleteCodeExamples)  
  
## <a name="prerequisites"></a><span data-ttu-id="a2c6c-122">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a2c6c-122">Prerequisites</span></span>  
 <span data-ttu-id="a2c6c-123">È necessario che sia installato nel computer Visual Studio 2012 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-123">Visual Studio 2012 or later must be installed on your computer.</span></span> <span data-ttu-id="a2c6c-124">Per altre informazioni, vedere il [sito Web di Microsoft](https://go.microsoft.com/fwlink/?LinkId=235233).</span><span class="sxs-lookup"><span data-stu-id="a2c6c-124">For more information, see the [Microsoft website](https://go.microsoft.com/fwlink/?LinkId=235233).</span></span>  
  
###  <a name="CreateWPFApp"></a> <span data-ttu-id="a2c6c-125">Per creare un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="a2c6c-125">To create a WPF application</span></span>  
  
1.  <span data-ttu-id="a2c6c-126">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-126">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="a2c6c-127">Nella barra dei menu scegliere **File**, **Nuovo**, **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-127">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="a2c6c-128">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="a2c6c-128">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="a2c6c-129">Nel **modelli installati** riquadro, scegliere Visual Basic e quindi scegliere **applicazione WPF** dall'elenco dei tipi di progetto.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-129">In the **Installed Templates** pane, choose Visual Basic, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="a2c6c-130">Nella casella di testo **Nome** immettere `AsyncExampleWPF` e quindi scegliere il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-130">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="a2c6c-131">Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-131">The new project appears in **Solution Explorer**.</span></span>  
  
##  <a name="BKMK_DesignWPFMainWin"></a>   
###  <a name="MainWindow"></a> <span data-ttu-id="a2c6c-132">Per progettare una finestra WPF MainWindow semplice</span><span class="sxs-lookup"><span data-stu-id="a2c6c-132">To design a simple WPF MainWindow</span></span>  
  
1.  <span data-ttu-id="a2c6c-133">Nell'Editor di codice di Visual Studio scegliere la scheda **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="a2c6c-133">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
2.  <span data-ttu-id="a2c6c-134">Se la finestra **Casella degli strumenti** non è visibile, aprire il menu **Visualizza** e quindi scegliere **Casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-134">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="a2c6c-135">Aggiungere un controllo **Button** e un controllo **TextBox** alla finestra **MainWindow**.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-135">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>  
  
4.  <span data-ttu-id="a2c6c-136">Evidenziare il controllo **TextBox** e nella finestra **Proprietà** impostare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2c6c-136">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="a2c6c-137">Impostare la proprietà **Nome** su `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-137">Set the **Name** property to `resultsTextBox`.</span></span>  
  
    -   <span data-ttu-id="a2c6c-138">Impostare la proprietà **Height** su 250.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-138">Set the **Height** property to 250.</span></span>  
  
    -   <span data-ttu-id="a2c6c-139">Impostare la proprietà **Width** su 500.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-139">Set the **Width** property to 500.</span></span>  
  
    -   <span data-ttu-id="a2c6c-140">Nel scheda **Testo** specificare un tipo di carattere a spaziatura fissa, ad esempio Lucida Console o Global Monospace.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-140">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>  
  
5.  <span data-ttu-id="a2c6c-141">Evidenziare il controllo **Button** e nella finestra **Proprietà** impostare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2c6c-141">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="a2c6c-142">Impostare la proprietà **Nome** su `startButton`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-142">Set the **Name** property to `startButton`.</span></span>  
  
    -   <span data-ttu-id="a2c6c-143">Modificare il valore della proprietà **Content** da **Button** in **Start**.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-143">Change the value of the **Content** property from **Button** to **Start**.</span></span>  
  
6.  <span data-ttu-id="a2c6c-144">Posizionare la casella di testo e il pulsante in modo che entrambi siano visualizzati nella finestra **MainWindow**.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-144">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>  
  
     <span data-ttu-id="a2c6c-145">Per altre informazioni su WPF XAML Designer, vedere [Creazione di un'interfaccia utente tramite XAML Designer](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="a2c6c-145">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>  
  
##  <a name="BKMK_AddReference"></a>   
###  <a name="AddRef"></a> <span data-ttu-id="a2c6c-146">Per aggiungere un riferimento</span><span class="sxs-lookup"><span data-stu-id="a2c6c-146">To add a reference</span></span>  
  
1.  <span data-ttu-id="a2c6c-147">In **Esplora soluzioni** evidenziare il nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-147">In **Solution Explorer**, highlight your project's name.</span></span>  
  
2.  <span data-ttu-id="a2c6c-148">Nella barra dei menu scegliere **Progetto**, **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-148">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="a2c6c-149">Verrà visualizzata la finestra di dialogo **Gestione riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-149">The **Reference Manager** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="a2c6c-150">Nella parte superiore della finestra di dialogo verificare che il progetto sia destinato a .NET Framework 4.5 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-150">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>  
  
4.  <span data-ttu-id="a2c6c-151">Nell'area **Assembly** scegliere **Framework** se non è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-151">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
5.  <span data-ttu-id="a2c6c-152">Nell'elenco dei nomi selezionare la casella di controllo **System.Net.Http**.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-152">In the list of names, select the **System.Net.Http** check box.</span></span>  
  
6.  <span data-ttu-id="a2c6c-153">Scegliere il pulsante **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-153">Choose the **OK** button to close the dialog box.</span></span>  
  
##  <a name="BKMK_AddStatesandDirs"></a>   
###  <a name="ImportsState"></a> <span data-ttu-id="a2c6c-154">Per aggiungere istruzioni Imports necessarie</span><span class="sxs-lookup"><span data-stu-id="a2c6c-154">To add necessary Imports statements</span></span>  
  
1.  <span data-ttu-id="a2c6c-155">Nelle **Esplora soluzioni**, aprire il menu di scelta rapida per XAML. vb e quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-155">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="a2c6c-156">Aggiungere il codice seguente `Imports` istruzioni all'inizio del file di codice, se non sono già presenti.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-156">Add the following `Imports` statements at the top of the code file if they’re not already present.</span></span>  
  
    ```vb  
    Imports System.Net.Http  
    Imports System.Net  
    Imports System.IO  
    ```  
  
##  <a name="BKMK_CreatSynchApp"></a>   
###  <a name="synchronous"></a> <span data-ttu-id="a2c6c-157">Per creare un'applicazione sincrona</span><span class="sxs-lookup"><span data-stu-id="a2c6c-157">To create a synchronous application</span></span>  
  
1.  <span data-ttu-id="a2c6c-158">Nella finestra di progettazione MainWindow. XAML fare doppio clic il **avviare** pulsante per creare il `startButton_Click` gestore dell'evento in XAML. vb.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-158">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="a2c6c-159">In XAML. vb, copiare il codice seguente nel corpo di `startButton_Click`:</span><span class="sxs-lookup"><span data-stu-id="a2c6c-159">In MainWindow.xaml.vb, copy the following code into the body of `startButton_Click`:</span></span>  
  
    ```vb  
    resultsTextBox.Clear()  
    SumPageSizes()  
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."  
    ```  
  
     <span data-ttu-id="a2c6c-160">Il codice chiama il metodo che controlla l'applicazione `SumPageSizes` e visualizza un messaggio quando il controllo torna a `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-160">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>  
  
3.  <span data-ttu-id="a2c6c-161">Il codice per la soluzione sincrona contiene i quattro metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2c6c-161">The code for the synchronous solution contains the following four methods:</span></span>  
  
    -   <span data-ttu-id="a2c6c-162">`SumPageSizes`, che ottiene un elenco di URL delle pagine Web da `SetUpURLList` e quindi chiama `GetURLContents` e `DisplayResults` per elaborare ogni URL.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-162">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>  
  
    -   <span data-ttu-id="a2c6c-163">`SetUpURLList`, che crea e restituisce un elenco di indirizzi web.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-163">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>  
  
    -   <span data-ttu-id="a2c6c-164">`GetURLContents`, che scarica il contenuto di ogni sito Web e restituisce il contenuto come matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-164">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>  
  
    -   <span data-ttu-id="a2c6c-165">`DisplayResults`, che visualizza il numero di byte nella matrice di byte per ogni URL.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-165">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>  
  
     <span data-ttu-id="a2c6c-166">Copiare i quattro metodi seguenti e incollarli nel `startButton_Click` gestore dell'evento in XAML. vb:</span><span class="sxs-lookup"><span data-stu-id="a2c6c-166">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.vb:</span></span>  
  
    ```vb  
    Private Sub SumPageSizes()  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        Dim total = 0  
        For Each url In urlList  
            ' GetURLContents returns the contents of url as a byte array.  
            Dim urlContents As Byte() = GetURLContents(url)  
  
            DisplayResults(url, urlContents)  
  
            ' Update the total.  
            total += urlContents.Length  
        Next  
  
        ' Display the total count for all of the web addresses.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "Total bytes returned:  {0}" & vbCrLf, total)  
    End Sub  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "https://msdn.microsoft.com",  
                "https://msdn.microsoft.com/library/hh290136.aspx",  
                "https://msdn.microsoft.com/library/ee256749.aspx",  
                "https://msdn.microsoft.com/library/hh290138.aspx",  
                "https://msdn.microsoft.com/library/hh290140.aspx",  
                "https://msdn.microsoft.com/library/dd470362.aspx",  
                "https://msdn.microsoft.com/library/aa578028.aspx",  
                "https://msdn.microsoft.com/library/ms404677.aspx",  
                "https://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    Private Function GetURLContents(url As String) As Byte()  
  
        ' The downloaded resource ends up in the variable named content.  
        Dim content = New MemoryStream()  
  
        ' Initialize an HttpWebRequest for the current URL.  
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
        ' Send the request to the Internet resource and wait for  
        ' the response.  
        ' Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.  
        Using response As WebResponse = webReq.GetResponse()  
            ' Get the data stream that is associated with the specified URL.  
            Using responseStream As Stream = response.GetResponseStream()  
                ' Read the bytes in responseStream and copy them to content.    
                responseStream.CopyTo(content)  
            End Using  
        End Using  
  
        ' Return the result as a byte array.  
        Return content.ToArray()  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "https://".  
        Dim displayURL = url.Replace("https://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
    ```  
  
##  <a name="BKMK_TestSynchSol"></a>   
###  <a name="testSynch"></a> <span data-ttu-id="a2c6c-167">Per eseguire il test della soluzione sincrona</span><span class="sxs-lookup"><span data-stu-id="a2c6c-167">To test the synchronous solution</span></span>  
  
1.  <span data-ttu-id="a2c6c-168">Premere il tasto F5 per eseguire il programma e quindi scegliere il pulsante **Start** .</span><span class="sxs-lookup"><span data-stu-id="a2c6c-168">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="a2c6c-169">Verrà visualizzato un output simile all'elenco seguente.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-169">Output that resembles the following list should appear.</span></span>  
  
    ```  
    msdn.microsoft.com/library/windows/apps/br211380.aspx        383832  
    msdn.microsoft.com                                            33964  
    msdn.microsoft.com/library/hh290136.aspx               225793  
    msdn.microsoft.com/library/ee256749.aspx               143577  
    msdn.microsoft.com/library/hh290138.aspx               237372  
    msdn.microsoft.com/library/hh290140.aspx               128279  
    msdn.microsoft.com/library/dd470362.aspx               157649  
    msdn.microsoft.com/library/aa578028.aspx               204457  
    msdn.microsoft.com/library/ms404677.aspx               176405  
    msdn.microsoft.com/library/ff730837.aspx               143474  
  
    Total bytes returned:  1834802  
  
    Control returned to startButton_Click.  
    ```  
  
     <span data-ttu-id="a2c6c-170">Si noti che sono necessari alcuni secondi per visualizzare i conteggi.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-170">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="a2c6c-171">Durante tale periodo, il thread dell'interfaccia utente viene bloccato mentre attende il download delle risorse richieste.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-171">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="a2c6c-172">Di conseguenza, è possibile spostare, ingrandire, ridurre o chiudere la finestra di visualizzazione dopo aver scelto il  pulsante **Start**.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-172">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="a2c6c-173">Queste operazioni hanno esito negativo finché non vengono visualizzati i conteggi dei byte.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-173">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="a2c6c-174">Se un sito Web non risponde, non si ha alcuna indicazione relativa al sito con esito negativo.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-174">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="a2c6c-175">È inoltre difficile interrompere l'attesa e chiudere il programma.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-175">It is difficult even to stop waiting and close the program.</span></span>  
  
##  <a name="BKMK_ConvertGtBtArr"></a>   
###  <a name="GetURLContents"></a> <span data-ttu-id="a2c6c-176">Per convertire GetURLContents in un metodo asincrono</span><span class="sxs-lookup"><span data-stu-id="a2c6c-176">To convert GetURLContents to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="a2c6c-177">Per convertire la soluzione sincrona in una soluzione asincrona, il punto di partenza migliore è in `GetURLContents` perché le chiamate al metodo <xref:System.Net.HttpWebRequest><xref:System.Net.HttpWebRequest.GetResponse%2A> e al metodo <xref:System.IO.Stream><xref:System.IO.Stream.CopyTo%2A> sono i punti in cui l'applicazione accede al Web.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-177">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest> method <xref:System.Net.HttpWebRequest.GetResponse%2A> and to the <xref:System.IO.Stream> method <xref:System.IO.Stream.CopyTo%2A> are where the application accesses the web.</span></span> <span data-ttu-id="a2c6c-178">.NET Framework semplifica la conversione fornendo versioni asincrone di entrambi i metodi.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-178">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>  
  
     <span data-ttu-id="a2c6c-179">Per altre informazioni sui modelli usati in `GetURLContents`, vedere <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-179">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a2c6c-180">Mentre si esegue la procedura descritta in questa procedura dettagliata, vengono visualizzati diversi errori del compilatore.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-180">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="a2c6c-181">È possibile ignorarli e continuare con la procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-181">You can ignore them and continue with the walkthrough.</span></span>  
  
     <span data-ttu-id="a2c6c-182">Modificare il metodo chiamato nella terza riga di `GetURLContents` da `GetResponse` nel metodo asincrono basato su attività <xref:System.Net.WebRequest.GetResponseAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-182">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>  
  
    ```vb  
    Using response As WebResponse = webReq.GetResponseAsync()  
    ```  
  
2.  <span data-ttu-id="a2c6c-183">`GetResponseAsync` restituisce <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-183">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="a2c6c-184">In questo caso, la *variabile di restituzione dell'attività*, `TResult`, è di tipo <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-184">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="a2c6c-185">L'attività rappresenta una promessa di creazione di un oggetto `WebResponse` effettivo dopo il download dei dati richiesti e il completamento dell'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-185">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>  
  
     <span data-ttu-id="a2c6c-186">Per recuperare il `WebResponse` valore dall'attività, applicare un' [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operatore per la chiamata a `GetResponseAsync`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-186">To retrieve the `WebResponse` value from the task, apply an [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>  
  
    ```vb  
    Using response As WebResponse = Await webReq.GetResponseAsync()  
    ```  
  
     <span data-ttu-id="a2c6c-187">L'operatore `GetURLContents` sospende l'esecuzione del metodo corrente `Await` fino al completamento dell'attività attesa.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-187">The `Await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="a2c6c-188">Nel frattempo il controllo viene restituito al chiamante del metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-188">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="a2c6c-189">In questo esempio, il metodo corrente è `GetURLContents` e il chiamante è `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-189">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="a2c6c-190">Quando l'attività è terminata, l'oggetto promesso `WebResponse` viene generato come valore dell'attività attesa e assegnato alla variabile `response`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-190">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>  
  
     <span data-ttu-id="a2c6c-191">L'istruzione precedente può essere suddivisa nelle due istruzioni seguenti per chiarire cosa accade.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-191">The previous statement can be separated into the following two statements to clarify what happens.</span></span>  
  
    ```vb  
    'Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()  
    'Using response As WebResponse = Await responseTask  
    ```  
  
     <span data-ttu-id="a2c6c-192">La chiamata a `webReq.GetResponseAsync` restituisce `Task(Of WebResponse)` o `Task<WebResponse>`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-192">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="a2c6c-193">Un oggetto `Await` operatore viene applicato all'attività per recuperare il `WebResponse` valore.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-193">Then an `Await` operator is applied to the task to retrieve the `WebResponse` value.</span></span>  
  
     <span data-ttu-id="a2c6c-194">Se il metodo asincrono ha operazioni da eseguire che non dipendono dal completamento dell'attività, il metodo può continuare l'esecuzione tra queste due istruzioni dopo la chiamata al metodo asincrono e prima che venga applicato l'operatore await.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-194">If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the await operator is applied.</span></span> <span data-ttu-id="a2c6c-195">Per esempi, vedere [procedura: effettuare più richieste Web in parallelo tramite Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) e [procedura: estendere la Async Walkthrough usando Task. whenall (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="a2c6c-195">For examples, see [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
3.  <span data-ttu-id="a2c6c-196">Poiché è stato aggiunto l'operatore `Await` nel passaggio precedente, verrà generato un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-196">Because you added the `Await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="a2c6c-197">L'operatore può essere usato solo nei metodi contrassegnati con il [Async](../../../../visual-basic/language-reference/modifiers/async.md) modificatore.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-197">The operator can be used only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="a2c6c-198">Ignorare l'errore mentre vengono ripetuti i passaggi di conversione per sostituire la chiamata a `CopyTo` con una chiamata a `CopyToAsync`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-198">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>  
  
    -   <span data-ttu-id="a2c6c-199">Modificare il nome del metodo chiamato in <xref:System.IO.Stream.CopyToAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-199">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>  
  
    -   <span data-ttu-id="a2c6c-200">Il metodo `CopyTo` o `CopyToAsync` copia i byte nel relativo argomento `content` e non restituisce un valore significativo.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-200">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="a2c6c-201">Nella versione sincrona, la chiamata a `CopyTo` è un'istruzione semplice che non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-201">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="a2c6c-202">La versione asincrona `CopyToAsync` restituisce <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-202">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="a2c6c-203">L'attività è analoga a "Task(void)" e consente l'attesa del metodo.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-203">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="a2c6c-204">Applicare `Await` o `await` alla chiamata a `CopyToAsync`, come mostrato nel codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-204">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>  
  
        ```vb  
        Await responseStream.CopyToAsync(content)  
        ```  
  
         <span data-ttu-id="a2c6c-205">L'istruzione precedente abbrevia le due righe di codice riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-205">The previous statement abbreviates the following two lines of code.</span></span>  
  
        ```vb  
        ' CopyToAsync returns a Task, not a Task<T>.  
        'Dim copyTask As Task = responseStream.CopyToAsync(content)  
  
        ' When copyTask is completed, content contains a copy of  
        ' responseStream.  
        'Await copyTask  
        ```  
  
4.  <span data-ttu-id="a2c6c-206">A questo punto, non rimane che modificare la firma del metodo in `GetURLContents`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-206">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="a2c6c-207">È possibile usare la `Await` operatore solo nei metodi contrassegnati con il [Async](../../../../visual-basic/language-reference/modifiers/async.md) modificatore.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-207">You can use the `Await` operator only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="a2c6c-208">Aggiungere il modificatore per contrassegnare il metodo come *metodo async*, come mostrato nel codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-208">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>  
  
    ```vb  
    Private Async Function GetURLContents(url As String) As Byte()  
    ```  
  
5.  <span data-ttu-id="a2c6c-209">Il tipo restituito di un metodo asincrono può essere solo <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-209">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="a2c6c-210">In Visual Basic, il metodo deve essere `Function` che restituisce `Task` o `Task(Of T)` oppure il metodo deve essere `Sub`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-210">In Visual Basic, the method must be a `Function` that returns a `Task` or a `Task(Of T)`, or the method must be a `Sub`.</span></span> <span data-ttu-id="a2c6c-211">In genere, un `Sub` metodo viene utilizzato solo in un gestore eventi asincrono, in cui `Sub` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-211">Typically, a `Sub` method  is used only in an async event handler, where `Sub` is required.</span></span> <span data-ttu-id="a2c6c-212">In altri casi, si utilizza `Task(T)` se il metodo completato include un' [restituire](../../../../visual-basic/language-reference/statements/return-statement.md) istruzione che restituisce un valore di tipo T e userai `Task` se il metodo completato non restituisce un valore significativo.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-212">In other cases, you use `Task(T)` if the completed method has a [Return](../../../../visual-basic/language-reference/statements/return-statement.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span>  
  
     <span data-ttu-id="a2c6c-213">Per altre informazioni, vedere [tipi restituiti asincroni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="a2c6c-213">For more information, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
     <span data-ttu-id="a2c6c-214">Il metodo `GetURLContents` dispone di un'istruzione return che restituisce una matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-214">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="a2c6c-215">Pertanto, il tipo restituito della versione asincrona è Task(T), dove T è una matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-215">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="a2c6c-216">Apportare le modifiche seguenti nella firma del metodo:</span><span class="sxs-lookup"><span data-stu-id="a2c6c-216">Make the following changes in the method signature:</span></span>  
  
    -   <span data-ttu-id="a2c6c-217">Cambiare il tipo restituito in `Task(Of Byte())`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-217">Change the return type to `Task(Of Byte())`.</span></span>  
  
    -   <span data-ttu-id="a2c6c-218">Per convenzione, i metodi asincroni presentano nomi che terminano in "Async". Rinominare pertanto il metodo `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-218">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>  
  
     <span data-ttu-id="a2c6c-219">Nel codice seguente sono illustrate queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-219">The following code shows these changes.</span></span>  
  
    ```vb  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
    ```  
  
     <span data-ttu-id="a2c6c-220">Dopo aver apportato queste modifiche, la conversione di `GetURLContents` in un metodo asincrono è completa.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-220">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>  
  
##  <a name="BKMK_ConvertSumPagSzs"></a>   
###  <a name="SumPageSizes"></a> <span data-ttu-id="a2c6c-221">Per Convertire SumPageSizes in un metodo asincrono</span><span class="sxs-lookup"><span data-stu-id="a2c6c-221">To convert SumPageSizes to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="a2c6c-222">Ripetere i passaggi della procedura precedente per `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-222">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="a2c6c-223">In primo luogo, modificare la chiamata a `GetURLContents` in una chiamata asincrona.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-223">First, change the call to `GetURLContents` to an asynchronous call.</span></span>  
  
    -   <span data-ttu-id="a2c6c-224">Modificare il nome del metodo chiamato da `GetURLContents` in `GetURLContentsAsync`, se non è ancora stato fatto.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-224">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>  
  
    -   <span data-ttu-id="a2c6c-225">Applicare `Await` all'attività restituita da `GetURLContentsAsync` per ottenere il valore della matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-225">Apply `Await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>  
  
     <span data-ttu-id="a2c6c-226">Nel codice seguente sono illustrate queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-226">The following code shows these changes.</span></span>  
  
    ```vb  
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
    ```  
  
     <span data-ttu-id="a2c6c-227">L'assegnazione precedente abbrevia le due righe di codice riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-227">The previous assignment abbreviates the following two lines of code.</span></span>  
  
    ```vb  
    ' GetURLContentsAsync returns a task. At completion, the task   
    ' produces a byte array.   
    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)   
    'Dim urlContents As Byte() = Await getContentsTask  
    ```  
  
2.  <span data-ttu-id="a2c6c-228">Apportare le modifiche seguenti nella firma del metodo:</span><span class="sxs-lookup"><span data-stu-id="a2c6c-228">Make the following changes in the method's signature:</span></span>  
  
    -   <span data-ttu-id="a2c6c-229">Contrassegnare il metodo con il modificatore `Async`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-229">Mark the method with the `Async` modifier.</span></span>  
  
    -   <span data-ttu-id="a2c6c-230">Aggiungere "Async" al nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-230">Add "Async" to the method name.</span></span>  
  
    -   <span data-ttu-id="a2c6c-231">In questo caso non esiste alcuna variabile di restituzione dell'attività, T, perché `SumPageSizesAsync` non restituisce un valore per T. Il metodo non ha alcuna istruzione `Return`. Tuttavia, il metodo deve restituire `Task` per poter essere un metodo di tipo awaitable.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-231">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `Return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="a2c6c-232">Pertanto, modificare il tipo di metodo dalla `Sub` a `Function`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-232">Therefore, change the method type from `Sub` to `Function`.</span></span> <span data-ttu-id="a2c6c-233">Il tipo restituito della funzione è `Task`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-233">The return type of the function is `Task`.</span></span>  
  
     <span data-ttu-id="a2c6c-234">Nel codice seguente sono illustrate queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-234">The following code shows these changes.</span></span>  
  
    ```vb  
    Private Async Function SumPageSizesAsync() As Task  
    ```  
  
     <span data-ttu-id="a2c6c-235">La conversione di `SumPageSizes` in `SumPageSizesAsync` è completa.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-235">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>  
  
##  <a name="BKMK_Cnvrtbttn1"></a>   
###  <a name="startButton"></a> <span data-ttu-id="a2c6c-236">Per convertire startButton_Click in un metodo asincrono</span><span class="sxs-lookup"><span data-stu-id="a2c6c-236">To convert startButton_Click to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="a2c6c-237">Nel gestore eventi modificare il nome del metodo chiamato da `SumPageSizes` in `SumPageSizesAsync`, se non è ancora stato fatto.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-237">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>  
  
2.  <span data-ttu-id="a2c6c-238">Poiché `SumPageSizesAsync` è un metodo asincrono, modificare il codice nel gestore eventi in modo che attenda il risultato.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-238">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>  
  
     <span data-ttu-id="a2c6c-239">La chiamata a `SumPageSizesAsync` rispecchia la chiamata a `CopyToAsync` in `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-239">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="a2c6c-240">La chiamata restituisce `Task` e non `Task(T)`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-240">The call returns a `Task`, not a `Task(T)`.</span></span>  
  
     <span data-ttu-id="a2c6c-241">Come nelle procedure precedenti, è possibile convertire la chiamata tramite una o due istruzioni.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-241">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="a2c6c-242">Nel codice seguente sono illustrate queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-242">The following code shows these changes.</span></span>  
  
    ```vb  
    '' One-step async call.  
    Await SumPageSizesAsync()  
  
    ' Two-step async call.  
    'Dim sumTask As Task = SumPageSizesAsync()  
    'Await sumTask  
    ```  
  
3.  <span data-ttu-id="a2c6c-243">Per impedire la reentrancy accidentale dell'operazione, aggiungere l'istruzione seguente all'inizio di `startButton_Click` per disabilitare il pulsante **Start**.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-243">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>  
  
    ```vb  
    ' Disable the button until the operation is complete.  
    startButton.IsEnabled = False  
    ```  
  
     <span data-ttu-id="a2c6c-244">È possibile riabilitare il pulsante alla fine del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-244">You can reenable the button at the end of the event handler.</span></span>  
  
    ```vb  
    ' Reenable the button in case you want to run the operation again.  
    startButton.IsEnabled = True  
    ```  
  
     <span data-ttu-id="a2c6c-245">Per altre informazioni sulla reentrancy, vedere [gestione della Reentrancy nelle applicazioni asincrone (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span><span class="sxs-lookup"><span data-stu-id="a2c6c-245">For more information about reentrancy, see [Handling Reentrancy in Async Apps (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span></span>  
  
4.  <span data-ttu-id="a2c6c-246">Aggiungere infine il modificatore `Async` alla dichiarazione, in modo che il gestore eventi possa attendere `SumPagSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-246">Finally, add the `Async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>  
  
    ```vb  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
    ```  
  
     <span data-ttu-id="a2c6c-247">In genere, i nomi dei gestori eventi non vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-247">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="a2c6c-248">Il tipo restituito non viene modificato in `Task` perché i gestori eventi devono essere `Sub` routine in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-248">The return type isn’t changed to `Task` because event handlers must be `Sub` procedures in Visual Basic.</span></span>  
  
     <span data-ttu-id="a2c6c-249">La conversione del progetto dall'elaborazione sincrona a quella asincrona è completa.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-249">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>  
  
##  <a name="BKMK_testAsynchSolution"></a>   
###  <a name="testAsynch"></a> <span data-ttu-id="a2c6c-250">Per eseguire il test della soluzione asincrona</span><span class="sxs-lookup"><span data-stu-id="a2c6c-250">To test the asynchronous solution</span></span>  
  
1.  <span data-ttu-id="a2c6c-251">Premere il tasto F5 per eseguire il programma e quindi scegliere il pulsante **Start** .</span><span class="sxs-lookup"><span data-stu-id="a2c6c-251">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
2.  <span data-ttu-id="a2c6c-252">Viene visualizzato un output simile all'output della soluzione sincrona.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-252">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="a2c6c-253">Esistono tuttavia le differenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2c6c-253">However, notice the following differences.</span></span>  
  
    -   <span data-ttu-id="a2c6c-254">I risultati non vengono restituiti contemporaneamente, al termine dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-254">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="a2c6c-255">Ad esempio, entrambi i programmi contengono una riga in `startButton_Click` che consente di cancellare la casella di testo.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-255">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="a2c6c-256">Lo scopo è quello di cancellare il contenuto della casella di testo tra le esecuzioni se si sceglie il pulsante **Start** per la seconda volta, dopo la visualizzazione di un set di risultati.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-256">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="a2c6c-257">Nella versione sincrona la casella di testo viene cancellata prima della seconda visualizzazione dei conteggi, ovvero quando vengono completati i download e il thread dell'interfaccia utente è libero di eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-257">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="a2c6c-258">Nella versione asincrona, la casella di testo viene cancellata subito dopo aver scelto il pulsante **Start**.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-258">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>  
  
    -   <span data-ttu-id="a2c6c-259">È importante notare che il thread dell'interfaccia utente non è bloccato durante il download.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-259">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="a2c6c-260">È possibile spostare o ridimensionare la finestra durante il download, il conteggio e la visualizzazione delle risorse Web.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-260">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="a2c6c-261">Se uno dei siti Web è lento o non risponde, è possibile annullare l'operazione scegliendo il pulsante **Chiudi** (il simbolo x su sfondo rosso nell'angolo superiore destro).</span><span class="sxs-lookup"><span data-stu-id="a2c6c-261">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>  
  
##  <a name="BKMK_ReplaceGetByteArrayAsync"></a>   
###  <a name="GetURLContentsAsync"></a> <span data-ttu-id="a2c6c-262">Per sostituire GetURLContentsAsync con un metodo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a2c6c-262">To replace method GetURLContentsAsync with a .NET Framework method</span></span>  
  
1.  <span data-ttu-id="a2c6c-263">.NET Framework 4.5 fornisce molti metodi asincroni che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-263">The .NET Framework 4.5 provides many async methods that you can use.</span></span> <span data-ttu-id="a2c6c-264">Uno di essi, il <xref:System.Net.Http.HttpClient> metodo <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, risulta utile in modo specifico per questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-264">One of them, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, does just what you need for this walkthrough.</span></span> <span data-ttu-id="a2c6c-265">È possibile usarlo al posto del metodo `GetURLContentsAsync` creato in una procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-265">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>  
  
     <span data-ttu-id="a2c6c-266">Il primo passaggio consiste nel creare un oggetto `HttpClient` nel metodo `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-266">The first step is to create an `HttpClient` object in method `SumPageSizesAsync`.</span></span> <span data-ttu-id="a2c6c-267">Aggiungere la dichiarazione seguente all'inizio del metodo.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-267">Add the following declaration at the start of the method.</span></span>  
  
    ```vb  
    ' Declare an HttpClient object and increase the buffer size. The  
    ' default buffer size is 65,536.  
    Dim client As HttpClient =  
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
    ```  
  
2.  <span data-ttu-id="a2c6c-268">In `SumPageSizesAsync,` sostituire la chiamata al metodo `GetURLContentsAsync` con una chiamata al metodo `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-268">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>  
  
    ```vb  
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
    ```  
  
3.  <span data-ttu-id="a2c6c-269">Rimuovere o impostare come commento il metodo `GetURLContentsAsync` precedentemente scritto.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-269">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>  
  
4.  <span data-ttu-id="a2c6c-270">Premere il tasto F5 per eseguire il programma e quindi scegliere il pulsante **Start** .</span><span class="sxs-lookup"><span data-stu-id="a2c6c-270">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="a2c6c-271">Il comportamento di questa versione del progetto deve corrispondere al comportamento descritto nella procedura "Per eseguire il test della soluzione asincrona" ma con un intervento ridotto da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-271">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>  
  
##  <a name="BKMK_CompleteCodeExamples"></a> <span data-ttu-id="a2c6c-272">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2c6c-272">Example</span></span>  
 <span data-ttu-id="a2c6c-273">Il codice seguente contiene l'esempio completo della conversione da soluzione sincrona a soluzione asincrona usando il metodo `GetURLContentsAsync` asincrono precedentemente scritto.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-273">The following code contains the full example of the conversion from a synchronous to an asynchronous solution by using the asynchronous `GetURLContentsAsync` method that you wrote.</span></span> <span data-ttu-id="a2c6c-274">Si noti che è molto simile alla soluzione sincrona originale.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-274">Notice that it strongly resembles the original, synchronous solution.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        ' Disable the button until the operation is complete.  
        startButton.IsEnabled = False  
  
        resultsTextBox.Clear()  
  
        '' One-step async call.  
        Await SumPageSizesAsync()  
  
        ' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
  
        ' Reenable the button in case you want to run the operation again.  
        startButton.IsEnabled = True  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        Dim total = 0  
        For Each url In urlList  
            Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
  
            ' The previous line abbreviates the following two assignment statements.  
  
            '//<snippet21>  
            ' GetURLContentsAsync returns a task. At completion, the task  
            ' produces a byte array.  
            'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)  
            'Dim urlContents As Byte() = Await getContentsTask  
  
            DisplayResults(url, urlContents)  
  
            ' Update the total.  
            total += urlContents.Length  
        Next  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "https://msdn.microsoft.com",  
                "https://msdn.microsoft.com/library/hh290136.aspx",  
                "https://msdn.microsoft.com/library/ee256749.aspx",  
                "https://msdn.microsoft.com/library/hh290138.aspx",  
                "https://msdn.microsoft.com/library/hh290140.aspx",  
                "https://msdn.microsoft.com/library/dd470362.aspx",  
                "https://msdn.microsoft.com/library/aa578028.aspx",  
                "https://msdn.microsoft.com/library/ms404677.aspx",  
                "https://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
        ' The downloaded resource ends up in the variable named content.  
        Dim content = New MemoryStream()  
  
        ' Initialize an HttpWebRequest for the current URL.  
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
        ' Send the request to the Internet resource and wait for  
        ' the response.  
        Using response As WebResponse = Await webReq.GetResponseAsync()  
  
            ' The previous statement abbreviates the following two statements.  
  
            'Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()  
            'Using response As WebResponse = Await responseTask  
  
            ' Get the data stream that is associated with the specified URL.  
            Using responseStream As Stream = response.GetResponseStream()  
                ' Read the bytes in responseStream and copy them to content.    
                Await responseStream.CopyToAsync(content)  
  
                ' The previous statement abbreviates the following two statements.  
  
                ' CopyToAsync returns a Task, not a Task<T>.  
                'Dim copyTask As Task = responseStream.CopyToAsync(content)  
  
                ' When copyTask is completed, content contains a copy of  
                ' responseStream.  
                'Await copyTask  
            End Using  
        End Using  
  
        ' Return the result as a byte array.  
        Return content.ToArray()  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "https://".  
        Dim displayURL = url.Replace("https://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
 <span data-ttu-id="a2c6c-275">Il codice seguente contiene l'esempio completo della soluzione che usa il metodo `HttpClient`, `GetByteArrayAsync`.</span><span class="sxs-lookup"><span data-stu-id="a2c6c-275">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        resultsTextBox.Clear()  
  
        ' Disable the button until the operation is complete.  
        startButton.IsEnabled = False  
  
        ' One-step async call.  
        Await SumPageSizesAsync()  
  
        '' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
  
        ' Reenable the button in case you want to run the operation again.  
        startButton.IsEnabled = True  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Declare an HttpClient object and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        Dim total = 0  
        For Each url In urlList  
            ' GetByteArrayAsync returns a task. At completion, the task  
            ' produces a byte array.  
            Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
  
            ' The following two lines can replace the previous assignment statement.  
            'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)  
            'Dim urlContents As Byte() = Await getContentsTask  
  
            DisplayResults(url, urlContents)  
  
            ' Update the total.  
            total += urlContents.Length  
        Next  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "https://msdn.microsoft.com",  
                "https://msdn.microsoft.com/library/hh290136.aspx",  
                "https://msdn.microsoft.com/library/ee256749.aspx",  
                "https://msdn.microsoft.com/library/hh290138.aspx",  
                "https://msdn.microsoft.com/library/hh290140.aspx",  
                "https://msdn.microsoft.com/library/dd470362.aspx",  
                "https://msdn.microsoft.com/library/aa578028.aspx",  
                "https://msdn.microsoft.com/library/ms404677.aspx",  
                "https://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "https://".  
        Dim displayURL = url.Replace("https://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2c6c-276">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2c6c-276">See Also</span></span>  
 <span data-ttu-id="a2c6c-277">[Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) (Esempio asincrono: accesso alla procedura dettagliata Web (C# e Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2c6c-277">[Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)</span></span>  
 [<span data-ttu-id="a2c6c-278">Operatore Await</span><span class="sxs-lookup"><span data-stu-id="a2c6c-278">Await Operator</span></span>](../../../../visual-basic/language-reference/operators/await-operator.md)  
 [<span data-ttu-id="a2c6c-279">Async</span><span class="sxs-lookup"><span data-stu-id="a2c6c-279">Async</span></span>](../../../../visual-basic/language-reference/modifiers/async.md)  
 [<span data-ttu-id="a2c6c-280">Programmazione asincrona con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2c6c-280">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="a2c6c-281">Tipi restituiti asincroni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2c6c-281">Async Return Types (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)  
 [<span data-ttu-id="a2c6c-282">Programmazione asincrona basata su attività</span><span class="sxs-lookup"><span data-stu-id="a2c6c-282">Task-based Asynchronous Programming (TAP)</span></span>](https://go.microsoft.com/fwlink/?LinkId=204847)  
 [<span data-ttu-id="a2c6c-283">Procedura: Estendere la procedura dettagliata asincrona tramite Task.WhenAll (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2c6c-283">How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)  
 [<span data-ttu-id="a2c6c-284">Procedura: Eseguire più richieste Web in parallelo tramite async e await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2c6c-284">How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
