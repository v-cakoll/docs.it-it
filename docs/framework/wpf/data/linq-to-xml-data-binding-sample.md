---
title: Esempio di data binding LINQ to XML
ms.date: 10/22/2019
ms.topic: sample
helpviewer_keywords:
- linq to xml data binding sample
ms.openlocfilehash: aac814e4768a863a93e69e34cd18c941a9b35c89
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920937"
---
# <a name="linq-to-xml-data-binding-sample"></a><span data-ttu-id="34cba-102">Esempio di LINQ to XML data binding</span><span class="sxs-lookup"><span data-stu-id="34cba-102">LINQ to XML data binding sample</span></span>

<span data-ttu-id="34cba-103">Questo articolo descrive l'esempio LinqToXmlDataBinding, un'app Windows Presentation Foundation (WPF) che associa i componenti dell'interfaccia utente a un'origine dati XML incorporata.</span><span class="sxs-lookup"><span data-stu-id="34cba-103">This article describes the LinqToXmlDataBinding sample, a Windows Presentation Foundation (WPF) app that binds user interface components to an embedded XML data source.</span></span>

## <a name="overview"></a><span data-ttu-id="34cba-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="34cba-104">Overview</span></span>

<span data-ttu-id="34cba-105">L'esempio LinqToXmlDataBinding è un'app Windows Presentation Foundation (WPF) che contiene C# i file di origine XAML e.</span><span class="sxs-lookup"><span data-stu-id="34cba-105">The LinqToXmlDataBinding sample is a Windows Presentation Foundation (WPF) app that contains C# and XAML source files.</span></span> <span data-ttu-id="34cba-106">Un documento XML incorporato definisce un elenco di libri.</span><span class="sxs-lookup"><span data-stu-id="34cba-106">An embedded XML document defines a list of books.</span></span> <span data-ttu-id="34cba-107">L'app consente all'utente di visualizzare, aggiungere, eliminare e modificare le voci del libro.</span><span class="sxs-lookup"><span data-stu-id="34cba-107">The app enables the user to view, add, delete, and edit the book entries.</span></span>

<span data-ttu-id="34cba-108">Sono disponibili due file di origine principali:</span><span class="sxs-lookup"><span data-stu-id="34cba-108">There are two primary source files:</span></span>

- <span data-ttu-id="34cba-109">[L2DBForm.xaml](l2dbform-xaml-source-code.md): contiene il codice della dichiarazione XAML per l'interfaccia utente della finestra principale.</span><span class="sxs-lookup"><span data-stu-id="34cba-109">[L2DBForm.xaml](l2dbform-xaml-source-code.md) contains the XAML declaration code for the user interface (UI) of the main window.</span></span> <span data-ttu-id="34cba-110">Contiene inoltre una sezione di risorse della finestra che definisce un provider di dati e un documento XML incorporato per gli elenchi di libri.</span><span class="sxs-lookup"><span data-stu-id="34cba-110">It also contains a window resource section that defines a data provider and an embedded XML document for the book listings.</span></span>

- <span data-ttu-id="34cba-111">[L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md): contiene i metodi di inizializzazione e gestione eventi associati all'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="34cba-111">[L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md) contains the initialization and event-handling methods associated with the UI.</span></span>

<span data-ttu-id="34cba-112">La finestra principale è divisa nelle quattro sezioni di interfaccia utente verticali descritte di seguito:</span><span class="sxs-lookup"><span data-stu-id="34cba-112">The main window is divided into the following four vertical UI sections:</span></span>

- <span data-ttu-id="34cba-113">**XML**: visualizza l'origine XML non elaborata dell'elenco di libri incorporato.</span><span class="sxs-lookup"><span data-stu-id="34cba-113">**XML** displays the raw XML source of the embedded book listing.</span></span>

- <span data-ttu-id="34cba-114">**Book List**: visualizza le voci relative ai libri come testo standard e consente all'utente di selezionare ed eliminare singole voci.</span><span class="sxs-lookup"><span data-stu-id="34cba-114">**Book List** displays the book entries as standard text and enables the user to select and delete individual entries.</span></span>

- <span data-ttu-id="34cba-115">**Edit Selected Book**: consente all'utente di modificare i valori associati alla voce attualmente selezionata.</span><span class="sxs-lookup"><span data-stu-id="34cba-115">**Edit Selected Book** enables the user to edit the values associated with the currently selected book entry.</span></span>

- <span data-ttu-id="34cba-116">**Add New Book**: consente di creare una nuova voce in base ai valori immessi dall'utente.</span><span class="sxs-lookup"><span data-stu-id="34cba-116">**Add New Book** enables the creation of a new book entry based on values entered by the user.</span></span>

## <a name="run-the-sample"></a><span data-ttu-id="34cba-117">Eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="34cba-117">Run the sample</span></span>

<span data-ttu-id="34cba-118">Questa sezione illustra come creare e compilare il progetto LinqToXmlDataBinding in Visual Studio e come eseguire l'app LinqToXmlDataBinding Windows Presentation Foundation (WPF) risultante.</span><span class="sxs-lookup"><span data-stu-id="34cba-118">This section shows how to create and build the LinqToXmlDataBinding project in Visual Studio, and how to run the resulting LinqToXmlDataBinding Windows Presentation Foundation (WPF) app.</span></span>

### <a name="create-the-project"></a><span data-ttu-id="34cba-119">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="34cba-119">Create the project</span></span>

1. <span data-ttu-id="34cba-120">Aprire Visual Studio e creare un'**app WPF** in C# denominata **LinqToXmlDataBinding**.</span><span class="sxs-lookup"><span data-stu-id="34cba-120">Open Visual Studio and create a C# **WPF App** named **LinqToXmlDataBinding**.</span></span>

   <span data-ttu-id="34cba-121">Il progetto dovrebbe avere come destinazione .NET Framework 3.5 (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="34cba-121">The project should target the .NET Framework 3.5 (or later).</span></span>

1. <span data-ttu-id="34cba-122">Se non sono già presenti, aggiungere i riferimenti di progetto per i seguenti assembly .NET:</span><span class="sxs-lookup"><span data-stu-id="34cba-122">If not already present, add project references for the following .NET assemblies:</span></span>

    - <span data-ttu-id="34cba-123">System.Data</span><span class="sxs-lookup"><span data-stu-id="34cba-123">System.Data</span></span>
    - <span data-ttu-id="34cba-124">System.Data.DataSetExtensions</span><span class="sxs-lookup"><span data-stu-id="34cba-124">System.Data.DataSetExtensions</span></span>
    - <span data-ttu-id="34cba-125">System.Xml</span><span class="sxs-lookup"><span data-stu-id="34cba-125">System.Xml</span></span>
    - <span data-ttu-id="34cba-126">System.Xml</span><span class="sxs-lookup"><span data-stu-id="34cba-126">System.Xml</span></span>

1. <span data-ttu-id="34cba-127">Compilare la soluzione premendo **CTRL**+**MAIUSC**+**B** ed eseguirla premendo **F5**.</span><span class="sxs-lookup"><span data-stu-id="34cba-127">Build the solution by pressing **Ctrl**+**Shift**+**B**, then run it by pressing **F5**.</span></span>

   <span data-ttu-id="34cba-128">Il progetto dovrebbe essere compilato senza errori ed eseguito come applicazione WPF generica.</span><span class="sxs-lookup"><span data-stu-id="34cba-128">The project should compile without errors and run as a generic WPF application.</span></span>

### <a name="add-code"></a><span data-ttu-id="34cba-129">Aggiungi codice</span><span class="sxs-lookup"><span data-stu-id="34cba-129">Add code</span></span>

1. <span data-ttu-id="34cba-130">In **Esplora soluzioni** rinominare il file di origine **Window1.xaml** in **L2XDBForm.xaml**.</span><span class="sxs-lookup"><span data-stu-id="34cba-130">In **Solution Explorer**, rename the source file **Window1.xaml** to **L2XDBForm.xaml**.</span></span>

   <span data-ttu-id="34cba-131">Il file di origine dipendente Window1.xaml.cs viene rinominato automaticamente in L2XDBForm.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="34cba-131">The dependent source file Window1.xaml.cs is automatically renamed to L2XDBForm.xaml.cs.</span></span>

1. <span data-ttu-id="34cba-132">Sostituire il codice sorgente trovato nel file **L2XDBForm. XAML** con il [codice sorgente L2DBForm. XAML](l2dbform-xaml-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="34cba-132">Replace the source code found in the file **L2XDBForm.xaml** with the [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span> <span data-ttu-id="34cba-133">Usare la visualizzazione Origine per usare questo file.</span><span class="sxs-lookup"><span data-stu-id="34cba-133">Use the XAML source view to work with this file.</span></span>

1. <span data-ttu-id="34cba-134">Analogamente, sostituire l'origine in **L2XDBForm.XAML.cs** con il [codice sorgente L2DBForm.XAML.cs](l2dbform-xaml-cs-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="34cba-134">Similarly, replace the source in **L2XDBForm.xaml.cs** with the [L2DBForm.xaml.cs source code](l2dbform-xaml-cs-source-code.md).</span></span>

1. <span data-ttu-id="34cba-135">Nel file **app. XAML**sostituire tutte le occorrenze della stringa **Window1. XAML** con **L2XDBForm. XAML**.</span><span class="sxs-lookup"><span data-stu-id="34cba-135">In the file **App.xaml**, replace all occurrences of the string **Window1.xaml** with **L2XDBForm.xaml**.</span></span>

1. <span data-ttu-id="34cba-136">Premere **CTRL**+**MAIUSC**+**B** per compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="34cba-136">Build the solution by pressing **Ctrl**+**Shift**+**B**.</span></span>

### <a name="run-the-app"></a><span data-ttu-id="34cba-137">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="34cba-137">Run the app</span></span>

<span data-ttu-id="34cba-138">L'app LinqToXmlDataBinding consente all'utente di visualizzare e modificare un elenco di libri archiviati come elemento XML incorporato.</span><span class="sxs-lookup"><span data-stu-id="34cba-138">The LinqToXmlDataBinding app enables the user to view and manipulate a list of books that's stored as an embedded XML element.</span></span> <span data-ttu-id="34cba-139">Eseguire l'app premendo **F5** (Avvia debug) o **CTRL**+**F5** (avvia senza eseguire debug).</span><span class="sxs-lookup"><span data-stu-id="34cba-139">Run the app by pressing **F5** (Start Debugging) or **Ctrl**+**F5** (Start Without Debugging).</span></span>

<span data-ttu-id="34cba-140">Viene visualizzata una finestra con il titolo **WPF Data Binding using LINQ to XML** (Data binding WPF con LINQ to XML).</span><span class="sxs-lookup"><span data-stu-id="34cba-140">A program window with the title **WPF Data Binding using LINQ to XML** appears.</span></span>

<span data-ttu-id="34cba-141">Nella sezione superiore dell'interfaccia utente viene visualizzato il **codice XML** non elaborato che rappresenta l'elenco di libri.</span><span class="sxs-lookup"><span data-stu-id="34cba-141">The top section of the UI displays the raw **XML** that represents the book list.</span></span> <span data-ttu-id="34cba-142">Viene visualizzato tramite un controllo <xref:System.Windows.Controls.TextBlock> WPF che non consente l'interazione tramite mouse o tastiera.</span><span class="sxs-lookup"><span data-stu-id="34cba-142">It is displayed using a WPF <xref:System.Windows.Controls.TextBlock> control, which does not enable interaction through the mouse or keyboard.</span></span>

<span data-ttu-id="34cba-143">Nella seconda sezione verticale, denominata **Book List**, vengono visualizzati i libri in un elenco ordinato in testo normale.</span><span class="sxs-lookup"><span data-stu-id="34cba-143">The second vertical section, labeled **Book List**, displays the books as a plain text ordered list.</span></span> <span data-ttu-id="34cba-144">Viene usato un controllo <xref:System.Windows.Controls.ListBox> che consente la selezione tramite mouse o tastiera.</span><span class="sxs-lookup"><span data-stu-id="34cba-144">It uses a <xref:System.Windows.Controls.ListBox> control that enables selection though the mouse or keyboard.</span></span>

### <a name="add-and-delete-books"></a><span data-ttu-id="34cba-145">Aggiungere ed eliminare libri</span><span class="sxs-lookup"><span data-stu-id="34cba-145">Add and delete books</span></span>

<span data-ttu-id="34cba-146">Per aggiungere un nuovo libro all'elenco, immettere i valori nei controlli **ID** e **valore** <xref:System.Windows.Controls.TextBox> nell'ultima sezione, **Aggiungi nuovo libro**, quindi selezionare **Aggiungi libro**.</span><span class="sxs-lookup"><span data-stu-id="34cba-146">To add a new book to the list, enter values into the **ID** and **Value** <xref:System.Windows.Controls.TextBox> controls in the last section, **Add New Book**, and then select **Add Book**.</span></span> <span data-ttu-id="34cba-147">Il libro viene aggiunto all'elenco sia nel libro che negli elenchi XML.</span><span class="sxs-lookup"><span data-stu-id="34cba-147">The book is appended to the list in both the book and XML listings.</span></span> <span data-ttu-id="34cba-148">In questo programma i valori di input non vengono convalidati.</span><span class="sxs-lookup"><span data-stu-id="34cba-148">This program does not validate input values.</span></span>

<span data-ttu-id="34cba-149">Per eliminare un libro esistente dall'elenco, selezionarlo nella sezione **Book List** e quindi selezionare **Rimuovi book selezionato**.</span><span class="sxs-lookup"><span data-stu-id="34cba-149">To delete an existing book from the list, select it in the **Book List** section, and then select **Remove Selected Book**.</span></span> <span data-ttu-id="34cba-150">La voce del libro viene rimossa sia dal libro che dagli elenchi di origini XML non elaborate.</span><span class="sxs-lookup"><span data-stu-id="34cba-150">The book entry is removed from both the book and the raw XML source listings.</span></span>

### <a name="edit-a-book-entry"></a><span data-ttu-id="34cba-151">Modificare una voce di libro</span><span class="sxs-lookup"><span data-stu-id="34cba-151">Edit a book entry</span></span>

1. <span data-ttu-id="34cba-152">Selezionare la voce del libro nella seconda sezione, **Book List**.</span><span class="sxs-lookup"><span data-stu-id="34cba-152">Select the book entry in the second **Book List** section.</span></span>

   <span data-ttu-id="34cba-153">I valori correnti vengono visualizzati nella sezione **Edit Selected Book** .</span><span class="sxs-lookup"><span data-stu-id="34cba-153">Its current values are displayed in the **Edit Selected Book** section.</span></span>

1. <span data-ttu-id="34cba-154">Modificare i valori usando la tastiera.</span><span class="sxs-lookup"><span data-stu-id="34cba-154">Edit the values using the keyboard.</span></span> <span data-ttu-id="34cba-155">Non appena <xref:System.Windows.Controls.TextBox> controllo perde lo stato attivo, le modifiche vengono propagate automaticamente all'origine XML e agli elenchi di libri.</span><span class="sxs-lookup"><span data-stu-id="34cba-155">As soon as either <xref:System.Windows.Controls.TextBox> control loses focus, changes are automatically propagated to the XML source and book listings.</span></span>
