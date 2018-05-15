---
title: Modifica di file e directory in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- files [Visual Basic], reading text
- reading files [Visual Basic], text
- I/O [Visual Basic], walkthroughs
- text, writing to files
- text, reading from files
- reading text from files [Visual Basic], walkthroughs
- Visual Basic code, file access
- files [Visual Basic], writing text
- I/O [Visual Basic], writing text to files
- file access, walkthroughs
- writing to files [Visual Basic], walkthroughs
- I/O [Visual Basic], reading text from files
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
caps.latest.revision: 49
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 12461cc99ec03ed87924c894e23740f9d76385ed
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-manipulating-files-and-directories-in-visual-basic"></a><span data-ttu-id="c13f5-102">Procedura dettagliata: modifica di file e directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c13f5-102">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>
<span data-ttu-id="c13f5-103">Questa procedura dettagliata offre un'introduzione ai principi di base degli elementi I/O di file in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c13f5-103">This walkthrough provides an introduction to the fundamentals of file I/O in Visual Basic.</span></span> <span data-ttu-id="c13f5-104">Descrive come creare una piccola applicazione in cui vengono elencati ed esaminati i file di testo di una directory.</span><span class="sxs-lookup"><span data-stu-id="c13f5-104">It describes how to create a small application that lists and examines text files in a directory.</span></span> <span data-ttu-id="c13f5-105">Per ogni file di testo selezionato, l'applicazione specifica gli attributi di file e la prima riga del contenuto.</span><span class="sxs-lookup"><span data-stu-id="c13f5-105">For each selected text file, the application provides file attributes and the first line of content.</span></span> <span data-ttu-id="c13f5-106">È disponibile un'opzione per la scrittura di informazioni in un file di log.</span><span class="sxs-lookup"><span data-stu-id="c13f5-106">There is an option to write information to a log file.</span></span>  
  
 <span data-ttu-id="c13f5-107">In questa procedura dettagliata vengono usati i membri di `My.Computer.FileSystem Object`, che sono disponibili in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c13f5-107">This walkthrough uses members of the `My.Computer.FileSystem Object`, which are available in Visual Basic.</span></span> <span data-ttu-id="c13f5-108">Per altre informazioni, vedere <xref:Microsoft.VisualBasic.FileIO.FileSystem>.</span><span class="sxs-lookup"><span data-stu-id="c13f5-108">See <xref:Microsoft.VisualBasic.FileIO.FileSystem> for more information.</span></span> <span data-ttu-id="c13f5-109">Al termine della procedura dettagliata è riportato un esempio equivalente che usa le classi dello spazio dei nomi <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="c13f5-109">At the end of the walkthrough, an equivalent example is provided that uses classes from the <xref:System.IO> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-the-project"></a><span data-ttu-id="c13f5-110">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="c13f5-110">To create the project</span></span>  
  
1.  <span data-ttu-id="c13f5-111">Scegliere **Nuovo progetto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="c13f5-111">On the **File** menu, click **New Project**.</span></span>  
  
     <span data-ttu-id="c13f5-112">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="c13f5-112">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="c13f5-113">Nel riquadro **Modelli installati** espandere **Visual Basic**, quindi fare clic su **Windows**.</span><span class="sxs-lookup"><span data-stu-id="c13f5-113">In the **Installed Templates** pane, expand **Visual Basic**, and then click **Windows**.</span></span> <span data-ttu-id="c13f5-114">Nel riquadro **Modelli** al centro scegliere **Windows Forms Application**.</span><span class="sxs-lookup"><span data-stu-id="c13f5-114">In the **Templates** pane in the middle, click **Windows Forms Application**.</span></span>  
  
3.  <span data-ttu-id="c13f5-115">Nella casella **Nome** digitare `FileExplorer` per impostare il nome del progetto e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c13f5-115">In the **Name** box, type `FileExplorer` to set the project name, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c13f5-116">Visual Studio aggiunge il progetto a **Esplora soluzioni** e viene aperto Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c13f5-116">Visual Studio adds the project to **Solution Explorer**, and the Windows Forms Designer opens.</span></span>  
  
4.  <span data-ttu-id="c13f5-117">Aggiungere i controlli della tabella seguente al form e impostare i valori corrispondenti per le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="c13f5-117">Add the controls in the following table to the form, and set the corresponding values for their properties.</span></span>  
  
    |<span data-ttu-id="c13f5-118">Control</span><span class="sxs-lookup"><span data-stu-id="c13f5-118">Control</span></span>|<span data-ttu-id="c13f5-119">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c13f5-119">Property</span></span>|<span data-ttu-id="c13f5-120">Valore</span><span class="sxs-lookup"><span data-stu-id="c13f5-120">Value</span></span>|  
    |-------------|--------------|-----------|  
    |<span data-ttu-id="c13f5-121">**ListBox**</span><span class="sxs-lookup"><span data-stu-id="c13f5-121">**ListBox**</span></span>|<span data-ttu-id="c13f5-122">**Name**</span><span class="sxs-lookup"><span data-stu-id="c13f5-122">**Name**</span></span>|`filesListBox`|  
    |<span data-ttu-id="c13f5-123">**Pulsante**</span><span class="sxs-lookup"><span data-stu-id="c13f5-123">**Button**</span></span>|<span data-ttu-id="c13f5-124">**Name**</span><span class="sxs-lookup"><span data-stu-id="c13f5-124">**Name**</span></span><br /><br /> <span data-ttu-id="c13f5-125">**per**</span><span class="sxs-lookup"><span data-stu-id="c13f5-125">**Text**</span></span>|`browseButton`<br /><br /> <span data-ttu-id="c13f5-126">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="c13f5-126">**Browse**</span></span>|  
    |<span data-ttu-id="c13f5-127">**Pulsante**</span><span class="sxs-lookup"><span data-stu-id="c13f5-127">**Button**</span></span>|<span data-ttu-id="c13f5-128">**Name**</span><span class="sxs-lookup"><span data-stu-id="c13f5-128">**Name**</span></span><br /><br /> <span data-ttu-id="c13f5-129">**per**</span><span class="sxs-lookup"><span data-stu-id="c13f5-129">**Text**</span></span>|`examineButton`<br /><br /> <span data-ttu-id="c13f5-130">**Esaminare**</span><span class="sxs-lookup"><span data-stu-id="c13f5-130">**Examine**</span></span>|  
    |<span data-ttu-id="c13f5-131">**CheckBox**</span><span class="sxs-lookup"><span data-stu-id="c13f5-131">**CheckBox**</span></span>|<span data-ttu-id="c13f5-132">**Name**</span><span class="sxs-lookup"><span data-stu-id="c13f5-132">**Name**</span></span><br /><br /> <span data-ttu-id="c13f5-133">**per**</span><span class="sxs-lookup"><span data-stu-id="c13f5-133">**Text**</span></span>|`saveCheckBox`<br /><br /> <span data-ttu-id="c13f5-134">**Salva risultati**</span><span class="sxs-lookup"><span data-stu-id="c13f5-134">**Save Results**</span></span>|  
    |<span data-ttu-id="c13f5-135">**FolderBrowserDialog**</span><span class="sxs-lookup"><span data-stu-id="c13f5-135">**FolderBrowserDialog**</span></span>|<span data-ttu-id="c13f5-136">**Name**</span><span class="sxs-lookup"><span data-stu-id="c13f5-136">**Name**</span></span>|`FolderBrowserDialog1`|  
  
### <a name="to-select-a-folder-and-list-files-in-a-folder"></a><span data-ttu-id="c13f5-137">Per selezionare una cartella ed elencare file di una cartella</span><span class="sxs-lookup"><span data-stu-id="c13f5-137">To select a folder, and list files in a folder</span></span>  
  
1.  <span data-ttu-id="c13f5-138">Creare un gestore eventi `Click` per `browseButton` facendo doppio clic sul controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="c13f5-138">Create a `Click` event handler for `browseButton` by double-clicking the control on the form.</span></span> <span data-ttu-id="c13f5-139">Verrà aperto l'Editor di codice.</span><span class="sxs-lookup"><span data-stu-id="c13f5-139">The Code Editor opens.</span></span>  
  
2.  <span data-ttu-id="c13f5-140">Aggiungere il codice seguente al gestore eventi `Click`.</span><span class="sxs-lookup"><span data-stu-id="c13f5-140">Add the following code to the `Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#103](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_1.vb)]  
  
     <span data-ttu-id="c13f5-141">La chiamata a `FolderBrowserDialog1.ShowDialog` apre la finestra di dialogo **Sfoglia per cartelle**.</span><span class="sxs-lookup"><span data-stu-id="c13f5-141">The `FolderBrowserDialog1.ShowDialog` call opens the **Browse For Folder** dialog box.</span></span> <span data-ttu-id="c13f5-142">Dopo che l'utente ha fatto clic su **OK**, la proprietà <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> viene inviata come argomento al metodo `ListFiles`, che viene aggiunto nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="c13f5-142">After the user clicks **OK**, the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property is sent as an argument to the `ListFiles` method, which is added in the next step.</span></span>  
  
3.  <span data-ttu-id="c13f5-143">Aggiungere il seguente metodo `ListFiles`.</span><span class="sxs-lookup"><span data-stu-id="c13f5-143">Add the following `ListFiles` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#104](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_2.vb)]  
  
     <span data-ttu-id="c13f5-144">Questo codice per prima cosa cancella il contenuto dell'oggetto **ListBox**.</span><span class="sxs-lookup"><span data-stu-id="c13f5-144">This code first clears the **ListBox**.</span></span>  
  
     <span data-ttu-id="c13f5-145">Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> recupera quindi una raccolta di stringhe, una per ogni file presente nella directory.</span><span class="sxs-lookup"><span data-stu-id="c13f5-145">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> method then retrieves a collection of strings, one for each file in the directory.</span></span> <span data-ttu-id="c13f5-146">Il metodo `GetFiles` accetta un argomento dei criteri di ricerca per recuperare i file che corrispondono a un criterio specifico.</span><span class="sxs-lookup"><span data-stu-id="c13f5-146">The `GetFiles` method accepts a search pattern argument to retrieve files that match a particular pattern.</span></span> <span data-ttu-id="c13f5-147">In questo esempio vengono restituiti solo i file con estensione TXT.</span><span class="sxs-lookup"><span data-stu-id="c13f5-147">In this example, only files that have the extension .txt are returned.</span></span>  
  
     <span data-ttu-id="c13f5-148">Le stringhe restituite dal metodo `GetFiles` vengono quindi aggiunte all'oggetto **ListBox**.</span><span class="sxs-lookup"><span data-stu-id="c13f5-148">The strings that are returned by the `GetFiles` method are then added to the **ListBox**.</span></span>  
  
4.  <span data-ttu-id="c13f5-149">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c13f5-149">Run the application.</span></span> <span data-ttu-id="c13f5-150">Fare clic sul pulsante **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="c13f5-150">Click the **Browse** button.</span></span> <span data-ttu-id="c13f5-151">Nella finestra di dialogo **Sfoglia per cartelle** passare a una cartella che contiene file TXT, quindi selezionare la cartella e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c13f5-151">In the **Browse For Folder** dialog box, browse to a folder that contains .txt files, and then select the folder and click **OK**.</span></span>  
  
     <span data-ttu-id="c13f5-152">L'oggetto `ListBox` contiene un elenco di file TXT presenti nella cartella selezionata.</span><span class="sxs-lookup"><span data-stu-id="c13f5-152">The `ListBox` contains a list of .txt files in the selected folder.</span></span>  
  
5.  <span data-ttu-id="c13f5-153">Arrestare l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c13f5-153">Stop running the application.</span></span>  
  
### <a name="to-obtain-attributes-of-a-file-and-content-from-a-text-file"></a><span data-ttu-id="c13f5-154">Per ottenere gli attributi di un file e il contenuto di un file di testo</span><span class="sxs-lookup"><span data-stu-id="c13f5-154">To obtain attributes of a file, and content from a text file</span></span>  
  
1.  <span data-ttu-id="c13f5-155">Creare un gestore eventi `Click` per `examineButton` facendo doppio clic sul controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="c13f5-155">Create a `Click` event handler for `examineButton` by double-clicking the control on the form.</span></span>  
  
2.  <span data-ttu-id="c13f5-156">Aggiungere il codice seguente al gestore eventi `Click`.</span><span class="sxs-lookup"><span data-stu-id="c13f5-156">Add the following code to the `Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#105](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_3.vb)]  
  
     <span data-ttu-id="c13f5-157">Il codice verifica se un elemento è selezionato nell'oggetto `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="c13f5-157">The code verifies that an item is selected in the `ListBox`.</span></span> <span data-ttu-id="c13f5-158">Ottiene quindi la voce del percorso del file da `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="c13f5-158">It then obtains the file path entry from the `ListBox`.</span></span> <span data-ttu-id="c13f5-159">Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> viene usato per verificare se il file esiste ancora.</span><span class="sxs-lookup"><span data-stu-id="c13f5-159">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> method is used to check whether the file still exists.</span></span>  
  
     <span data-ttu-id="c13f5-160">Il percorso del file viene inviato come argomento al metodo `GetTextForOutput`, che viene aggiunto nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="c13f5-160">The file path is sent as an argument to the `GetTextForOutput` method, which is added in the next step.</span></span> <span data-ttu-id="c13f5-161">Questo metodo restituisce una stringa che contiene informazioni sul file.</span><span class="sxs-lookup"><span data-stu-id="c13f5-161">This method returns a string that contains file information.</span></span> <span data-ttu-id="c13f5-162">Le informazioni sul file appaiono in un oggetto **MessageBox**.</span><span class="sxs-lookup"><span data-stu-id="c13f5-162">The file information appears in a **MessageBox**.</span></span>  
  
3.  <span data-ttu-id="c13f5-163">Aggiungere il seguente metodo `GetTextForOutput`.</span><span class="sxs-lookup"><span data-stu-id="c13f5-163">Add the following `GetTextForOutput` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#107](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_4.vb)]  
  
     <span data-ttu-id="c13f5-164">Il codice usa il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> per ottenere i parametri del file.</span><span class="sxs-lookup"><span data-stu-id="c13f5-164">The code uses the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method to obtain file parameters.</span></span> <span data-ttu-id="c13f5-165">I parametri del file vengono aggiunti a un oggetto <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="c13f5-165">The file parameters are added to a <xref:System.Text.StringBuilder>.</span></span>  
  
     <span data-ttu-id="c13f5-166">Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> legge il contenuto del file in un oggetto <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="c13f5-166">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> method reads the file contents into a <xref:System.IO.StreamReader>.</span></span> <span data-ttu-id="c13f5-167">La prima riga del contenuto viene ottenuta da `StreamReader` e viene aggiunta a `StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="c13f5-167">The first line of the contents is obtained from the `StreamReader` and is added to the `StringBuilder`.</span></span>  
  
4.  <span data-ttu-id="c13f5-168">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c13f5-168">Run the application.</span></span> <span data-ttu-id="c13f5-169">Fare clic su **Sfoglia** e passare a una cartella che contiene file TXT.</span><span class="sxs-lookup"><span data-stu-id="c13f5-169">Click **Browse**, and browse to a folder that contains .txt files.</span></span> <span data-ttu-id="c13f5-170">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c13f5-170">Click **OK**.</span></span>  
  
     <span data-ttu-id="c13f5-171">Selezionare un file in `ListBox`, quindi fare clic su **Esaminare**.</span><span class="sxs-lookup"><span data-stu-id="c13f5-171">Select a file in the `ListBox`, and then click **Examine**.</span></span> <span data-ttu-id="c13f5-172">L'oggetto `MessageBox` contiene le informazioni sul file.</span><span class="sxs-lookup"><span data-stu-id="c13f5-172">A `MessageBox` shows the file information.</span></span>  
  
5.  <span data-ttu-id="c13f5-173">Arrestare l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c13f5-173">Stop running the application.</span></span>  
  
### <a name="to-add-a-log-entry"></a><span data-ttu-id="c13f5-174">Per aggiungere una voce di log</span><span class="sxs-lookup"><span data-stu-id="c13f5-174">To add a log entry</span></span>  
  
1.  <span data-ttu-id="c13f5-175">Aggiungere il codice seguente alla fine del gestore eventi `examineButton_Click` .</span><span class="sxs-lookup"><span data-stu-id="c13f5-175">Add the following code to the end of the `examineButton_Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#106](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_5.vb)]  
  
     <span data-ttu-id="c13f5-176">Il codice imposta il percorso del file di log in modo da inserire il file di log nella stessa directory del file selezionato.</span><span class="sxs-lookup"><span data-stu-id="c13f5-176">The code sets the log file path to put the log file in the same directory as that of the selected file.</span></span> <span data-ttu-id="c13f5-177">Il testo della voce di log è impostato su data e ora correnti seguite dalle informazioni sul file.</span><span class="sxs-lookup"><span data-stu-id="c13f5-177">The text of the log entry is set to the current date and time followed by the file information.</span></span>  
  
     <span data-ttu-id="c13f5-178">Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>, con l'argomento `append` impostato su `True`, viene usato per creare la voce di log.</span><span class="sxs-lookup"><span data-stu-id="c13f5-178">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method, with the `append` argument set to `True`, is used to create the log entry.</span></span>  
  
2.  <span data-ttu-id="c13f5-179">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c13f5-179">Run the application.</span></span> <span data-ttu-id="c13f5-180">Individuare un file di testo, selezionarlo in `ListBox`, selezionare la casella di controllo **Salva risultati** e quindi fare clic su **Esaminare**.</span><span class="sxs-lookup"><span data-stu-id="c13f5-180">Browse to a text file, select it in the `ListBox`, select the **Save Results** check box, and then click **Examine**.</span></span> <span data-ttu-id="c13f5-181">Verificare che la voce di log sia scritta nel file `log.txt`.</span><span class="sxs-lookup"><span data-stu-id="c13f5-181">Verify that the log entry is written to the `log.txt` file.</span></span>  
  
3.  <span data-ttu-id="c13f5-182">Arrestare l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c13f5-182">Stop running the application.</span></span>  
  
### <a name="to-use-the-current-directory"></a><span data-ttu-id="c13f5-183">Per usare la directory corrente</span><span class="sxs-lookup"><span data-stu-id="c13f5-183">To use the current directory</span></span>  
  
1.  <span data-ttu-id="c13f5-184">Creare un gestore eventi per `Form1_Load` facendo doppio clic sul form.</span><span class="sxs-lookup"><span data-stu-id="c13f5-184">Create an event handler for `Form1_Load` by double-clicking the form.</span></span>  
  
2.  <span data-ttu-id="c13f5-185">Aggiungere il codice seguente al gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="c13f5-185">Add the following code to the event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#102](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_6.vb)]  
  
     <span data-ttu-id="c13f5-186">Questo codice imposta la directory predefinita del browser delle cartelle sulla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="c13f5-186">This code sets the default directory of the folder browser to the current directory.</span></span>  
  
3.  <span data-ttu-id="c13f5-187">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c13f5-187">Run the application.</span></span> <span data-ttu-id="c13f5-188">Quando si fa clic su **Sfoglia** per la prima volta la finestra di dialogo **Sfoglia per cartelle** si apre visualizzando la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="c13f5-188">When you click **Browse** the first time, the **Browse For Folder** dialog box opens to the current directory.</span></span>  
  
4.  <span data-ttu-id="c13f5-189">Arrestare l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c13f5-189">Stop running the application.</span></span>  
  
### <a name="to-selectively-enable-controls"></a><span data-ttu-id="c13f5-190">Per abilitare selettivamente i controlli</span><span class="sxs-lookup"><span data-stu-id="c13f5-190">To selectively enable controls</span></span>  
  
1.  <span data-ttu-id="c13f5-191">Aggiungere il seguente metodo `SetEnabled`.</span><span class="sxs-lookup"><span data-stu-id="c13f5-191">Add the following `SetEnabled` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#108](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_7.vb)]  
  
     <span data-ttu-id="c13f5-192">Il metodo `SetEnabled` abilita o disabilita i controlli a seconda se è selezionato un elemento nell'oggetto `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="c13f5-192">The `SetEnabled` method enables or disables controls depending on whether an item is selected in the `ListBox`.</span></span>  
  
2.  <span data-ttu-id="c13f5-193">Creare un gestore eventi `SelectedIndexChanged` per `filesListBox` facendo doppio clic sul controllo `ListBox` nel form.</span><span class="sxs-lookup"><span data-stu-id="c13f5-193">Create a `SelectedIndexChanged` event handler for `filesListBox` by double-clicking the `ListBox` control on the form.</span></span>  
  
3.  <span data-ttu-id="c13f5-194">Aggiungere una chiamata a `SetEnabled` nel nuovo gestore eventi `filesListBox_SelectedIndexChanged`.</span><span class="sxs-lookup"><span data-stu-id="c13f5-194">Add a call to `SetEnabled` in the new `filesListBox_SelectedIndexChanged` event handler.</span></span>  
  
4.  <span data-ttu-id="c13f5-195">Aggiungere una chiamata a `SetEnabled` alla fine del gestore eventi `browseButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="c13f5-195">Add a call to `SetEnabled` at the end of the `browseButton_Click` event handler.</span></span>  
  
5.  <span data-ttu-id="c13f5-196">Aggiungere una chiamata a `SetEnabled` alla fine del gestore eventi `Form1_Load`.</span><span class="sxs-lookup"><span data-stu-id="c13f5-196">Add a call to `SetEnabled` at the end of the `Form1_Load` event handler.</span></span>  
  
6.  <span data-ttu-id="c13f5-197">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c13f5-197">Run the application.</span></span> <span data-ttu-id="c13f5-198">La casella di controllo **Salva risultati** e il pulsante **Esaminare** sono disabilitati se non è selezionato un elemento in `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="c13f5-198">The **Save Results** check box and the **Examine** button are disabled if an item is not selected in the `ListBox`.</span></span>  
  
## <a name="full-example-using-mycomputerfilesystem"></a><span data-ttu-id="c13f5-199">Esempio completo di uso di My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="c13f5-199">Full example using My.Computer.FileSystem</span></span>  
 <span data-ttu-id="c13f5-200">Di seguito è riportato l'esempio completo.</span><span class="sxs-lookup"><span data-stu-id="c13f5-200">Following is the complete example.</span></span>  
  
 [!code-vb[VbVbcnMyFileSystem#101](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_8.vb)]  
  
## <a name="full-example-using-systemio"></a><span data-ttu-id="c13f5-201">Esempio completo usando System.IO</span><span class="sxs-lookup"><span data-stu-id="c13f5-201">Full example using System.IO</span></span>  
 <span data-ttu-id="c13f5-202">Nel seguente esempio equivalente vengono usate le classi dello spazio dei nomi <xref:System.IO> anziché gli oggetti `My.Computer.FileSystem`.</span><span class="sxs-lookup"><span data-stu-id="c13f5-202">The following equivalent example uses classes from the <xref:System.IO> namespace instead of using `My.Computer.FileSystem` objects.</span></span>  
  
 [!code-vb[VbVbcnMyFileSystem#111](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_9.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c13f5-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c13f5-203">See Also</span></span>  
 <xref:System.IO>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>  
 [<span data-ttu-id="c13f5-204">Procedura dettagliata: Modifica di file mediante i metodi .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c13f5-204">Walkthrough: Manipulating Files by Using .NET Framework Methods</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)
