---
title: Modifica di file con i metodi .NET Framework
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], walkthroughs
- text files [Visual Basic], writing to
- reading text files [Visual Basic]
- text, writing to files
- files [Visual Basic], searching
- StreamReader class, walkthroughs
- files [Visual Basic], accessing
- I/O [Visual Basic], writing text to files
- writing to files [Visual Basic], walkthroughs
- StreamWriter class, walkthroughs
- text files [Visual Basic], reading
- I/O [Visual Basic], reading text from files
ms.assetid: 7d2109eb-f98a-4389-b43d-30f384aaa7d5
ms.openlocfilehash: 9abb87f3f6cdefefef29eb37c2c2d4d15155e93d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406651"
---
# <a name="walkthrough-manipulating-files-by-using-net-framework-methods-visual-basic"></a><span data-ttu-id="47c66-102">Procedura dettagliata: modifica di file mediante i metodi .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47c66-102">Walkthrough: Manipulating Files by Using .NET Framework Methods (Visual Basic)</span></span>

<span data-ttu-id="47c66-103">Questa procedura dettagliata spiega come aprire e leggere un file usando la classe <xref:System.IO.StreamReader>, verificare se un file è accessibile, cercare una stringa all'interno di un file letto con un'istanza della classe <xref:System.IO.StreamReader> e scrivere in un file usando la classe <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="47c66-103">This walkthrough demonstrates how to open and read a file using the <xref:System.IO.StreamReader> class, check to see if a file is being accessed, search for a string within a file read with an instance of the <xref:System.IO.StreamReader> class, and write to a file using the <xref:System.IO.StreamWriter> class.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="creating-the-application"></a><span data-ttu-id="47c66-104">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="47c66-104">Creating the Application</span></span>

<span data-ttu-id="47c66-105">Avviare Visual Studio e iniziare il progetto creando un modulo che l'utente può usare per scrivere il file specificato.</span><span class="sxs-lookup"><span data-stu-id="47c66-105">Start Visual Studio and begin the project by creating a form that the user can use to write to the designated file.</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="47c66-106">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="47c66-106">To create the project</span></span>

1. <span data-ttu-id="47c66-107">Scegliere **Nuovo progetto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="47c66-107">On the **File** menu, select **New Project**.</span></span>

2. <span data-ttu-id="47c66-108">Nel riquadro **Nuovo progetto** fare clic su **Applicazione Windows**.</span><span class="sxs-lookup"><span data-stu-id="47c66-108">In the **New Project** pane, click **Windows Application**.</span></span>

3. <span data-ttu-id="47c66-109">Nella casella **nome** Digitare `MyDiary` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="47c66-109">In the **Name** box type `MyDiary` and click **OK**.</span></span>

     <span data-ttu-id="47c66-110">Visual Studio aggiunge il progetto a **Esplora soluzioni**e il **Progettazione Windows Form** viene aperto.</span><span class="sxs-lookup"><span data-stu-id="47c66-110">Visual Studio adds the project to **Solution Explorer**, and the **Windows Forms Designer** opens.</span></span>

4. <span data-ttu-id="47c66-111">Aggiungere i controlli della tabella seguente al form e impostare i valori corrispondenti per le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="47c66-111">Add the controls in the following table to the form and set the corresponding values for their properties.</span></span>

|<span data-ttu-id="47c66-112">**Object**</span><span class="sxs-lookup"><span data-stu-id="47c66-112">**Object**</span></span>|<span data-ttu-id="47c66-113">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="47c66-113">**Properties**</span></span>|<span data-ttu-id="47c66-114">**Valore**</span><span class="sxs-lookup"><span data-stu-id="47c66-114">**Value**</span></span>|
|---|---|---|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="47c66-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="47c66-115">**Name**</span></span><br /><br /> <span data-ttu-id="47c66-116">**Testo**</span><span class="sxs-lookup"><span data-stu-id="47c66-116">**Text**</span></span>|`Submit`<br /><br /> <span data-ttu-id="47c66-117">**Invia voce**</span><span class="sxs-lookup"><span data-stu-id="47c66-117">**Submit Entry**</span></span>|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="47c66-118">**Nome**</span><span class="sxs-lookup"><span data-stu-id="47c66-118">**Name**</span></span><br /><br /> <span data-ttu-id="47c66-119">**Testo**</span><span class="sxs-lookup"><span data-stu-id="47c66-119">**Text**</span></span>|`Clear`<br /><br /> <span data-ttu-id="47c66-120">**Cancella voce**</span><span class="sxs-lookup"><span data-stu-id="47c66-120">**Clear Entry**</span></span>|
|<xref:System.Windows.Forms.TextBox>|<span data-ttu-id="47c66-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="47c66-121">**Name**</span></span><br /><br /> <span data-ttu-id="47c66-122">**Testo**</span><span class="sxs-lookup"><span data-stu-id="47c66-122">**Text**</span></span><br /><br /> <span data-ttu-id="47c66-123">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="47c66-123">**Multiline**</span></span>|`Entry`<br /><br /> <span data-ttu-id="47c66-124">**Immettere un valore.**</span><span class="sxs-lookup"><span data-stu-id="47c66-124">**Please enter something.**</span></span><br /><br /> `False`|

## <a name="writing-to-the-file"></a><span data-ttu-id="47c66-125">Scrivere nel file</span><span class="sxs-lookup"><span data-stu-id="47c66-125">Writing to the File</span></span>

<span data-ttu-id="47c66-126">Per aggiungere la possibilità di scrivere in un file tramite l'applicazione, usare la classe <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="47c66-126">To add the ability to write to a file via the application, use the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="47c66-127">La classe <xref:System.IO.StreamWriter> è progettata per l'output di caratteri in una codifica particolare, mentre la classe <xref:System.IO.Stream> è progettata per l'input e l'output di byte.</span><span class="sxs-lookup"><span data-stu-id="47c66-127"><xref:System.IO.StreamWriter> is designed for character output in a particular encoding, whereas the <xref:System.IO.Stream> class is designed for byte input and output.</span></span> <span data-ttu-id="47c66-128">Usare la classe <xref:System.IO.StreamWriter> per scrivere righe di informazioni in un file di testo standard.</span><span class="sxs-lookup"><span data-stu-id="47c66-128">Use <xref:System.IO.StreamWriter> for writing lines of information to a standard text file.</span></span> <span data-ttu-id="47c66-129">Per altre informazioni sulla classe <xref:System.IO.StreamWriter>, vedere <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="47c66-129">For more information on the <xref:System.IO.StreamWriter> class, see <xref:System.IO.StreamWriter>.</span></span>

### <a name="to-add-writing-functionality"></a><span data-ttu-id="47c66-130">Per aggiungere la funzionalità di scrittura</span><span class="sxs-lookup"><span data-stu-id="47c66-130">To add writing functionality</span></span>

1. <span data-ttu-id="47c66-131">Scegliere **Codice** dal menu **Visualizza** per aprire l'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="47c66-131">From the **View** menu, choose **Code** to open the Code Editor.</span></span>

2. <span data-ttu-id="47c66-132">Poiché l'applicazione fa riferimento allo spazio dei nomi <xref:System.IO>, aggiungere le istruzioni seguenti all'inizio del codice, prima della dichiarazione di classe per il form, che inizia con `Public Class Form1`.</span><span class="sxs-lookup"><span data-stu-id="47c66-132">Because the application references the <xref:System.IO> namespace, add the following statements at the very beginning of your code, before the class declaration for the form, which begins `Public Class Form1`.</span></span>

     [!code-vb[VbVbcnMyFileSystem#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#35)]

     <span data-ttu-id="47c66-133">Prima di scrivere nel file è necessario creare un'istanza di una classe <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="47c66-133">Before writing to the file, you must create an instance of a <xref:System.IO.StreamWriter> class.</span></span>

3. <span data-ttu-id="47c66-134">Scegliere **Finestra di progettazione** dal menu **Visualizza** per tornare a **Progettazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="47c66-134">From the **View** menu, choose **Designer** to return to the **Windows Forms Designer**.</span></span> <span data-ttu-id="47c66-135">Fare doppio clic sul pulsante `Submit` per creare un gestore eventi <xref:System.Windows.Forms.Control.Click> per il pulsante e quindi aggiungere il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="47c66-135">Double-click the `Submit` button to create a <xref:System.Windows.Forms.Control.Click> event handler for the button, and then add the following code.</span></span>

     [!code-vb[VbVbcnMyFileSystem#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#36)]

> [!NOTE]
> <span data-ttu-id="47c66-136">L'ambiente di sviluppo integrato (IDE) di Visual Studio torna all'editor di codice e posiziona il punto di inserimento all'interno del gestore eventi in cui deve essere aggiunto il codice.</span><span class="sxs-lookup"><span data-stu-id="47c66-136">The Visual Studio Integrated Development Environment (IDE) will return to the Code Editor and position the insertion point within the event handler where you should add the code.</span></span>

1. <span data-ttu-id="47c66-137">Per scrivere nel file, usare il metodo <xref:System.IO.StreamWriter.Write%2A> della classe <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="47c66-137">To write to the file, use the <xref:System.IO.StreamWriter.Write%2A> method of the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="47c66-138">Aggiungere il codice seguente direttamente dopo `Dim fw As StreamWriter`.</span><span class="sxs-lookup"><span data-stu-id="47c66-138">Add the following code directly after `Dim fw As StreamWriter`.</span></span> <span data-ttu-id="47c66-139">Non è necessario preoccuparsi del fatto che venga generata un'eccezione se il file non viene trovato, poiché verrà creato se non esiste già.</span><span class="sxs-lookup"><span data-stu-id="47c66-139">You do not need to worry that an exception will be thrown if the file is not found, because it will be created if it does not already exist.</span></span>

     [!code-vb[VbVbcnMyFileSystem#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#37)]

2. <span data-ttu-id="47c66-140">Assicurarsi che l'utente non possa immettere uno spazio vuoto aggiungendo il codice seguente subito dopo `Dim ReadString As String`.</span><span class="sxs-lookup"><span data-stu-id="47c66-140">Make sure that the user cannot submit a blank entry by adding the following code directly after `Dim ReadString As String`.</span></span>

     [!code-vb[VbVbcnMyFileSystem#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#38)]

3. <span data-ttu-id="47c66-141">Poiché si tratta di un diario, l'utente dovrà assegnare una data a ogni voce.</span><span class="sxs-lookup"><span data-stu-id="47c66-141">Because this is a diary, the user will want to assign a date to each entry.</span></span> <span data-ttu-id="47c66-142">Inserire il codice seguente dopo `fw = New StreamWriter("C:\MyDiary.txt", True)` per impostare la variabile `Today` sulla data corrente.</span><span class="sxs-lookup"><span data-stu-id="47c66-142">Insert the following code after `fw = New StreamWriter("C:\MyDiary.txt", True)` to set the variable `Today` to the current date.</span></span>

     [!code-vb[VbVbcnMyFileSystem#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#39)]

4. <span data-ttu-id="47c66-143">Aggiungere infine il codice per cancellare <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="47c66-143">Finally, attach code to clear the <xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="47c66-144">Aggiungere il codice seguente all'evento <xref:System.Windows.Forms.Control.Click> del pulsante `Clear`.</span><span class="sxs-lookup"><span data-stu-id="47c66-144">Add the following code to the `Clear` button's <xref:System.Windows.Forms.Control.Click> event.</span></span>

     [!code-vb[VbVbcnMyFileSystem#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#40)]

## <a name="adding-display-features-to-the-diary"></a><span data-ttu-id="47c66-145">Aggiungere funzionalità di visualizzazione al diario</span><span class="sxs-lookup"><span data-stu-id="47c66-145">Adding Display Features to the Diary</span></span>

<span data-ttu-id="47c66-146">In questa sezione, si aggiunge una funzionalità che consente di visualizzare l'ultima voce dell'oggetto `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="47c66-146">In this section, you add a feature that displays the latest entry in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="47c66-147">È anche possibile aggiungere un oggetto <xref:System.Windows.Forms.ComboBox> che visualizza le diverse voci e da cui un utente può selezionare una voce da visualizzare nell'oggetto `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="47c66-147">You can also add a <xref:System.Windows.Forms.ComboBox> that displays various entries and from which a user can select an entry to display in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="47c66-148">Un'istanza della classe <xref:System.IO.StreamReader> legge da `MyDiary.txt`.</span><span class="sxs-lookup"><span data-stu-id="47c66-148">An instance of the <xref:System.IO.StreamReader> class reads from `MyDiary.txt`.</span></span> <span data-ttu-id="47c66-149">Come la classe <xref:System.IO.StreamWriter>, la classe <xref:System.IO.StreamReader> deve essere usata con file di testo.</span><span class="sxs-lookup"><span data-stu-id="47c66-149">Like the <xref:System.IO.StreamWriter> class, <xref:System.IO.StreamReader> is intended for use with text files.</span></span>

<span data-ttu-id="47c66-150">Per questa sezione della procedura, aggiungere i controlli della tabella seguente al form e impostare i valori corrispondenti per le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="47c66-150">For this section of the walkthrough, add the controls in the following table to the form and set the corresponding values for their properties.</span></span>

|<span data-ttu-id="47c66-151">Controllo</span><span class="sxs-lookup"><span data-stu-id="47c66-151">Control</span></span>|<span data-ttu-id="47c66-152">Proprietà</span><span class="sxs-lookup"><span data-stu-id="47c66-152">Properties</span></span>|<span data-ttu-id="47c66-153">Valori</span><span class="sxs-lookup"><span data-stu-id="47c66-153">Values</span></span>|
|-------------|----------------|------------|
|<xref:System.Windows.Forms.TextBox>|<span data-ttu-id="47c66-154">**Nome**</span><span class="sxs-lookup"><span data-stu-id="47c66-154">**Name**</span></span><br /><br /> <span data-ttu-id="47c66-155">**Visibile**</span><span class="sxs-lookup"><span data-stu-id="47c66-155">**Visible**</span></span><br /><br /> <span data-ttu-id="47c66-156">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="47c66-156">**Size**</span></span><br /><br /> <span data-ttu-id="47c66-157">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="47c66-157">**Multiline**</span></span>|`DisplayEntry`<br /><br /> `False`<br /><br /> `120,60`<br /><br /> `True`|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="47c66-158">**Nome**</span><span class="sxs-lookup"><span data-stu-id="47c66-158">**Name**</span></span><br /><br /> <span data-ttu-id="47c66-159">**Testo**</span><span class="sxs-lookup"><span data-stu-id="47c66-159">**Text**</span></span>|`Display`<br /><br /> <span data-ttu-id="47c66-160">**Schermo**</span><span class="sxs-lookup"><span data-stu-id="47c66-160">**Display**</span></span>|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="47c66-161">**Nome**</span><span class="sxs-lookup"><span data-stu-id="47c66-161">**Name**</span></span><br /><br /> <span data-ttu-id="47c66-162">**Testo**</span><span class="sxs-lookup"><span data-stu-id="47c66-162">**Text**</span></span>|`GetEntries`<br /><br /> <span data-ttu-id="47c66-163">**Ottieni voci**</span><span class="sxs-lookup"><span data-stu-id="47c66-163">**Get Entries**</span></span>|
|<xref:System.Windows.Forms.ComboBox>|<span data-ttu-id="47c66-164">**Nome**</span><span class="sxs-lookup"><span data-stu-id="47c66-164">**Name**</span></span><br /><br /> <span data-ttu-id="47c66-165">**Testo**</span><span class="sxs-lookup"><span data-stu-id="47c66-165">**Text**</span></span><br /><br /> <span data-ttu-id="47c66-166">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="47c66-166">**Enabled**</span></span>|`PickEntries`<br /><br /> <span data-ttu-id="47c66-167">**Seleziona una voce**</span><span class="sxs-lookup"><span data-stu-id="47c66-167">**Select an Entry**</span></span><br /><br /> `False`|

### <a name="to-populate-the-combo-box"></a><span data-ttu-id="47c66-168">Per popolare la casella combinata</span><span class="sxs-lookup"><span data-stu-id="47c66-168">To populate the combo box</span></span>

1. <span data-ttu-id="47c66-169">L'oggetto `PickEntries`<xref:System.Windows.Forms.ComboBox> viene usato per visualizzare le date in cui un utente immette le diverse voci, in modo che l'utente possa selezionare una voce da una data specifica.</span><span class="sxs-lookup"><span data-stu-id="47c66-169">The `PickEntries`<xref:System.Windows.Forms.ComboBox> is used to display the dates on which a user submits each entry, so the user can select an entry from a specific date.</span></span> <span data-ttu-id="47c66-170">Creare un gestore eventi <xref:System.Windows.Forms.Control.Click> per il pulsante `GetEntries` e aggiungervi il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="47c66-170">Create a <xref:System.Windows.Forms.Control.Click> event handler to the `GetEntries` button and add the following code.</span></span>

     [!code-vb[VbVbcnMyFileSystem#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#41)]

2. <span data-ttu-id="47c66-171">Per testare il codice, premere F5 per compilare l'applicazione e quindi fare clic su **Ottieni voci**.</span><span class="sxs-lookup"><span data-stu-id="47c66-171">To test your code, press F5 to compile the application, and then click **Get Entries**.</span></span> <span data-ttu-id="47c66-172">Fare clic sulla freccia giù nell'oggetto <xref:System.Windows.Forms.ComboBox> per visualizzare le date delle voci.</span><span class="sxs-lookup"><span data-stu-id="47c66-172">Click the drop-down arrow in the <xref:System.Windows.Forms.ComboBox> to display the entry dates.</span></span>

### <a name="to-choose-and-display-individual-entries"></a><span data-ttu-id="47c66-173">Per scegliere e visualizzare le singole voci</span><span class="sxs-lookup"><span data-stu-id="47c66-173">To choose and display individual entries</span></span>

1. <span data-ttu-id="47c66-174">Creare un gestore eventi <xref:System.Windows.Forms.Control.Click> per il pulsante `Display` e aggiungervi il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="47c66-174">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `Display` button and add the following code.</span></span>

     [!code-vb[VbVbcnMyFileSystem#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#42)]

2. <span data-ttu-id="47c66-175">Per testare il codice, premere F5 per compilare l'applicazione e quindi inviare una voce.</span><span class="sxs-lookup"><span data-stu-id="47c66-175">To test your code, press F5 to compile the application, and then submit an entry.</span></span> <span data-ttu-id="47c66-176">Fare clic su **Ottieni voci**, selezionare una voce in <xref:System.Windows.Forms.ComboBox> e quindi fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="47c66-176">Click **Get Entries**, select an entry from the <xref:System.Windows.Forms.ComboBox>, and then click **Display**.</span></span> <span data-ttu-id="47c66-177">Il contenuto della voce selezionata viene visualizzato nell'oggetto `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="47c66-177">The contents of the selected entry appear in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span>

## <a name="enabling-users-to-delete-or-modify-entries"></a><span data-ttu-id="47c66-178">Consentire agli utenti di eliminare o modificare le voci</span><span class="sxs-lookup"><span data-stu-id="47c66-178">Enabling Users to Delete or Modify Entries</span></span>

<span data-ttu-id="47c66-179">Infine, è possibile includere funzionalità aggiuntive che consentono agli utenti di eliminare o modificare una voce usando i pulsanti `DeleteEntry` e `EditEntry`.</span><span class="sxs-lookup"><span data-stu-id="47c66-179">Finally, you can include additional functionality enables users to delete or modify an entry by using `DeleteEntry` and `EditEntry` buttons.</span></span> <span data-ttu-id="47c66-180">Entrambi i pulsanti restano disabilitati a meno che non sia visualizzata una voce.</span><span class="sxs-lookup"><span data-stu-id="47c66-180">Both buttons remain disabled unless an entry is displayed.</span></span>

<span data-ttu-id="47c66-181">Aggiungere i controlli della tabella seguente al form e impostare i valori corrispondenti per le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="47c66-181">Add the controls in the following table to the form and set the corresponding values for their properties.</span></span>

|<span data-ttu-id="47c66-182">Controllo</span><span class="sxs-lookup"><span data-stu-id="47c66-182">Control</span></span>|<span data-ttu-id="47c66-183">Proprietà</span><span class="sxs-lookup"><span data-stu-id="47c66-183">Properties</span></span>|<span data-ttu-id="47c66-184">Valori</span><span class="sxs-lookup"><span data-stu-id="47c66-184">Values</span></span>|
|-------------|----------------|------------|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="47c66-185">**Nome**</span><span class="sxs-lookup"><span data-stu-id="47c66-185">**Name**</span></span><br /><br /> <span data-ttu-id="47c66-186">**Testo**</span><span class="sxs-lookup"><span data-stu-id="47c66-186">**Text**</span></span><br /><br /> <span data-ttu-id="47c66-187">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="47c66-187">**Enabled**</span></span>|`DeleteEntry`<br /><br /> <span data-ttu-id="47c66-188">**Elimina voce**</span><span class="sxs-lookup"><span data-stu-id="47c66-188">**Delete Entry**</span></span><br /><br /> `False`|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="47c66-189">**Nome**</span><span class="sxs-lookup"><span data-stu-id="47c66-189">**Name**</span></span><br /><br /> <span data-ttu-id="47c66-190">**Testo**</span><span class="sxs-lookup"><span data-stu-id="47c66-190">**Text**</span></span><br /><br /> <span data-ttu-id="47c66-191">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="47c66-191">**Enabled**</span></span>|`EditEntry`<br /><br /> <span data-ttu-id="47c66-192">**Modifica voce**</span><span class="sxs-lookup"><span data-stu-id="47c66-192">**Edit Entry**</span></span><br /><br /> `False`|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="47c66-193">**Nome**</span><span class="sxs-lookup"><span data-stu-id="47c66-193">**Name**</span></span><br /><br /> <span data-ttu-id="47c66-194">**Testo**</span><span class="sxs-lookup"><span data-stu-id="47c66-194">**Text**</span></span><br /><br /> <span data-ttu-id="47c66-195">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="47c66-195">**Enabled**</span></span>|`SubmitEdit`<br /><br /> <span data-ttu-id="47c66-196">**Invia modifica**</span><span class="sxs-lookup"><span data-stu-id="47c66-196">**Submit Edit**</span></span><br /><br /> `False`|

### <a name="to-enable-deletion-and-modification-of-entries"></a><span data-ttu-id="47c66-197">Per abilitare l'eliminazione e la modifica delle voci</span><span class="sxs-lookup"><span data-stu-id="47c66-197">To enable deletion and modification of entries</span></span>

1. <span data-ttu-id="47c66-198">Aggiungere il codice seguente all'evento <xref:System.Windows.Forms.Control.Click> del pulsante `Display`, dopo `DisplayEntry.Text = ReadString`.</span><span class="sxs-lookup"><span data-stu-id="47c66-198">Add the following code to the `Display` button's <xref:System.Windows.Forms.Control.Click> event, after `DisplayEntry.Text = ReadString`.</span></span>

     [!code-vb[VbVbcnMyFileSystem#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#43)]

2. <span data-ttu-id="47c66-199">Creare un gestore eventi <xref:System.Windows.Forms.Control.Click> per il pulsante `DeleteEntry` e aggiungervi il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="47c66-199">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `DeleteEntry` button and add the following code.</span></span>

     [!code-vb[VbVbcnMyFileSystem#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#44)]

3. <span data-ttu-id="47c66-200">Quando un utente visualizza una voce, il pulsante `EditEntry` viene abilitato.</span><span class="sxs-lookup"><span data-stu-id="47c66-200">When a user displays an entry, the `EditEntry` button becomes enabled.</span></span> <span data-ttu-id="47c66-201">Aggiungere il codice seguente all'evento <xref:System.Windows.Forms.Control.Click> del pulsante `Display` dopo `DisplayEntry.Text = ReadString`.</span><span class="sxs-lookup"><span data-stu-id="47c66-201">Add the following code to the <xref:System.Windows.Forms.Control.Click> event of the `Display` button after `DisplayEntry.Text = ReadString`.</span></span>

     [!code-vb[VbVbcnMyFileSystem#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#45)]

4. <span data-ttu-id="47c66-202">Creare un gestore eventi <xref:System.Windows.Forms.Control.Click> per il pulsante `EditEntry` e aggiungervi il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="47c66-202">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `EditEntry` button and add the following code.</span></span>

     [!code-vb[VbVbcnMyFileSystem#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#46)]

5. <span data-ttu-id="47c66-203">Creare un gestore eventi <xref:System.Windows.Forms.Control.Click> per il pulsante `SubmitEdit` e aggiungervi il codice seguente</span><span class="sxs-lookup"><span data-stu-id="47c66-203">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `SubmitEdit` button and add the following code</span></span>

     [!code-vb[VbVbcnMyFileSystem#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#47)]

<span data-ttu-id="47c66-204">Per testare il codice, premere F5 per compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="47c66-204">To test your code, press F5 to compile the application.</span></span> <span data-ttu-id="47c66-205">Fare clic su **Ottieni voci**, selezionare una voce e quindi fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="47c66-205">Click **Get Entries**, select an entry, and then click **Display**.</span></span> <span data-ttu-id="47c66-206">La voce viene visualizzata nell'oggetto `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="47c66-206">The entry appears in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="47c66-207">Fare clic su **Modifica voce**.</span><span class="sxs-lookup"><span data-stu-id="47c66-207">Click **Edit Entry**.</span></span> <span data-ttu-id="47c66-208">La voce viene visualizzata nell'oggetto `Entry`<xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="47c66-208">The entry appears in the `Entry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="47c66-209">Modificare la voce in `Entry` <xref:System.Windows.Forms.TextBox> e fare clic su **Invia modifica**.</span><span class="sxs-lookup"><span data-stu-id="47c66-209">Edit the entry in the `Entry`<xref:System.Windows.Forms.TextBox> and click **Submit Edit**.</span></span> <span data-ttu-id="47c66-210">Aprire il file `MyDiary.txt` per confermare la correzione.</span><span class="sxs-lookup"><span data-stu-id="47c66-210">Open the `MyDiary.txt` file to confirm your correction.</span></span> <span data-ttu-id="47c66-211">Ora selezionare una voce e fare clic su **Elimina voce**.</span><span class="sxs-lookup"><span data-stu-id="47c66-211">Now select an entry and click **Delete Entry**.</span></span> <span data-ttu-id="47c66-212">Quando l'oggetto <xref:System.Windows.Forms.MessageBox> chiede una conferma, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="47c66-212">When the <xref:System.Windows.Forms.MessageBox> requests confirmation, click **OK**.</span></span> <span data-ttu-id="47c66-213">Chiudere l'applicazione e aprire `MyDiary.txt` per confermare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="47c66-213">Close the application and open `MyDiary.txt` to confirm the deletion.</span></span>

## <a name="see-also"></a><span data-ttu-id="47c66-214">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47c66-214">See also</span></span>

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="47c66-215">Procedure dettagliate</span><span class="sxs-lookup"><span data-stu-id="47c66-215">Walkthroughs</span></span>](../../../walkthroughs.md)
