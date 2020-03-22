---
title: Memorizzazione e lettura di dati dagli Appunti
ms.date: 07/20/2015
helpviewer_keywords:
- Clipboard, storing data to (My.Computer.Clipboard)
- Clipboard, reading from (My.Computer.Clipboard)
- Clipboard
- My.Computer.Clipboard object, tasks
- data [Visual Basic], Clipboard
- reading data, from Clipboard
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
ms.openlocfilehash: 243fb237f3f9ba53f8b29079df08531c102c78dd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74349737"
---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a><span data-ttu-id="75b54-102">Archiviazione e lettura di dati negli Appunti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75b54-102">Storing data to and reading from the Clipboard (Visual Basic)</span></span>

<span data-ttu-id="75b54-103">Gli Appunti possono essere usati per archiviare i dati, ad esempio testo e immagini.</span><span class="sxs-lookup"><span data-stu-id="75b54-103">The Clipboard can be used to store data, such as text and images.</span></span> <span data-ttu-id="75b54-104">Poiché gli Appunti sono condivisi tra tutti i processi attivi, possono essere usati per trasferire dati tra di essi.</span><span class="sxs-lookup"><span data-stu-id="75b54-104">Because the Clipboard is shared by all active processes, it can be used to transfer data between them.</span></span> <span data-ttu-id="75b54-105">L'oggetto `My.Computer.Clipboard` consente di accedere facilmente agli Appunti per leggere e scrivere.</span><span class="sxs-lookup"><span data-stu-id="75b54-105">The `My.Computer.Clipboard` object allows you to easily access the Clipboard and to read from and write to it.</span></span>  
  
## <a name="reading-from-the-clipboard"></a><span data-ttu-id="75b54-106">Lettura dagli Appunti</span><span class="sxs-lookup"><span data-stu-id="75b54-106">Reading from the Clipboard</span></span>  

 <span data-ttu-id="75b54-107">Usare il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> per leggere il testo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="75b54-107">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> method to read the text in the Clipboard.</span></span> <span data-ttu-id="75b54-108">Il codice seguente legge il testo e lo visualizza in una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="75b54-108">The following code reads the text and displays it in a message box.</span></span> <span data-ttu-id="75b54-109">Per far funzionare l'esempio, gli Appunti devono contenere testo archiviato.</span><span class="sxs-lookup"><span data-stu-id="75b54-109">There must be text stored on the Clipboard for the example to run correctly.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#4)]  
  
 <span data-ttu-id="75b54-110">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="75b54-110">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="75b54-111">Nello strumento di selezione dei frammenti di codice il frammento di codice si trova in **Applicazioni Windows Form > Appunti**.</span><span class="sxs-lookup"><span data-stu-id="75b54-111">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.</span></span> <span data-ttu-id="75b54-112">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="75b54-112">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="75b54-113">Usare il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> per recuperare un'immagine dagli Appunti.</span><span class="sxs-lookup"><span data-stu-id="75b54-113">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> method to retrieve an image from the Clipboard.</span></span> <span data-ttu-id="75b54-114">Questo esempio verifica se è disponibile un'immagine negli Appunti prima di tentarne il recupero e assegnarlo a `PictureBox1`.</span><span class="sxs-lookup"><span data-stu-id="75b54-114">This example checks to see if there is an image on the Clipboard before retrieving it and assigning it to `PictureBox1`.</span></span>  
  
 [!code-vb[VbResourceTasks#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#16)]  
  
 <span data-ttu-id="75b54-115">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="75b54-115">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="75b54-116">Nello strumento di selezione dei frammenti di codice il frammento di codice si trova in **Applicazioni Windows Form > Appunti**. Per altre informazioni, vedere [Frammenti di codice](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="75b54-116">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="75b54-117">Gli elementi inseriti negli Appunti verranno mantenuti anche dopo l'arresto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="75b54-117">Items placed on the Clipboard will persist even after the application is shut down.</span></span>  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a><span data-ttu-id="75b54-118">Determinazione del tipo di file archiviati negli Appunti</span><span class="sxs-lookup"><span data-stu-id="75b54-118">Determining the type of file stored in the Clipboard</span></span>  

 <span data-ttu-id="75b54-119">I dati contenuti negli Appunti potrebbero avere diverse forme, ad esempio testo, file audio o immagine.</span><span class="sxs-lookup"><span data-stu-id="75b54-119">Data on the Clipboard may take a number of different forms, such as text, an audio file, or an image.</span></span> <span data-ttu-id="75b54-120">Per determinare il tipo di file negli Appunti, è possibile usare metodi quali <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> e <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.</span><span class="sxs-lookup"><span data-stu-id="75b54-120">In order to determine what sort of file is on the Clipboard, you can use methods such as <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A>, and <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.</span></span> <span data-ttu-id="75b54-121">Il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> può essere usato nel caso in cui si voglia controllare un formato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="75b54-121">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> method can be used if you have a custom format that you want to check.</span></span>  
  
 <span data-ttu-id="75b54-122">Usare la funzione `ContainsImage` per determinare se i dati contenuti negli Appunti costituiscono un'immagine.</span><span class="sxs-lookup"><span data-stu-id="75b54-122">Use the `ContainsImage` function to determine whether the data contained on the Clipboard is an image.</span></span> <span data-ttu-id="75b54-123">Il codice seguente consente di controllare se i dati costituiscono un'immagine e invia una segnalazione in merito.</span><span class="sxs-lookup"><span data-stu-id="75b54-123">The following code checks to see whether the data is an image and reports accordingly.</span></span>  
  
 [!code-vb[VbResourceTasks#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#13)]  
  
## <a name="clearing-the-clipboard"></a><span data-ttu-id="75b54-124">Cancellazione degli Appunti</span><span class="sxs-lookup"><span data-stu-id="75b54-124">Clearing the Clipboard</span></span>  

 <span data-ttu-id="75b54-125">Il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> cancella il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="75b54-125">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> method clears the Clipboard.</span></span> <span data-ttu-id="75b54-126">Poiché gli Appunti sono condivisi da altri processi, la cancellazione può avere conseguenze su tali processi.</span><span class="sxs-lookup"><span data-stu-id="75b54-126">Because the Clipboard is shared by other processes, clearing it may have an impact on those processes.</span></span>  
  
 <span data-ttu-id="75b54-127">Nell'esempio di codice seguente viene illustrato come utilizzare il metodo `Clear`.</span><span class="sxs-lookup"><span data-stu-id="75b54-127">The following code shows how to use the `Clear` method.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#3)]  
  
## <a name="writing-to-the-clipboard"></a><span data-ttu-id="75b54-128">Scrittura negli Appunti</span><span class="sxs-lookup"><span data-stu-id="75b54-128">Writing to the Clipboard</span></span>  

 <span data-ttu-id="75b54-129">Usare il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> per scrivere testo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="75b54-129">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> method to write text to the Clipboard.</span></span> <span data-ttu-id="75b54-130">Il codice seguente scrive la stringa "Questa è una stringa di prova" negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="75b54-130">The following code writes the string "This is a test string" to the Clipboard.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#1)]  
  
 <span data-ttu-id="75b54-131">Il metodo `SetText` può accettare un parametro di formato contenente un tipo di <xref:System.Windows.Forms.TextDataFormat>.</span><span class="sxs-lookup"><span data-stu-id="75b54-131">The `SetText` method can accept a format parameter that contains a type of <xref:System.Windows.Forms.TextDataFormat>.</span></span> <span data-ttu-id="75b54-132">Il codice seguente scrive la stringa "Questa è una stringa di prova" negli Appunti come testo RTF.</span><span class="sxs-lookup"><span data-stu-id="75b54-132">The following code writes the string "This is a test string" to the Clipboard as RTF text.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#2)]  
  
 <span data-ttu-id="75b54-133">Usare il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> per scrivere dati negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="75b54-133">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> method to write data to the Clipboard.</span></span> <span data-ttu-id="75b54-134">In questo esempio `DataObject` `dataChunk` viene scritto negli Appunti nel formato personalizzato `specialFormat`.</span><span class="sxs-lookup"><span data-stu-id="75b54-134">This example writes the `DataObject` `dataChunk` to the Clipboard in the custom format `specialFormat`.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#7)]  
  
 <span data-ttu-id="75b54-135">Usare il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> per scrivere dati audio negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="75b54-135">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> method to write audio data to the Clipboard.</span></span> <span data-ttu-id="75b54-136">Questo esempio crea la matrice di byte `musicReader`, legge il file `cool.wav` al suo interno e lo scrive quindi negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="75b54-136">This example creates the byte array `musicReader`, reads the file `cool.wav` into it, and then writes it to the Clipboard.</span></span>  
  
 [!code-vb[VbResourceTasks#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#5)]  
  
> [!IMPORTANT]
> <span data-ttu-id="75b54-137">Dal momento che gli Appunti sono accessibili da altri utenti, non usarli per archiviare informazioni sensibili, ad esempio password o dati riservati.</span><span class="sxs-lookup"><span data-stu-id="75b54-137">Because the Clipboard can be accessed by other users, do not use it to store sensitive information, such as passwords or confidential data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75b54-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75b54-138">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>
- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>
- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>
- [<span data-ttu-id="75b54-139">Procedura: leggere dati oggetto da un file XMLHow to: Read Object Data from an XML File</span><span class="sxs-lookup"><span data-stu-id="75b54-139">How to: Read Object Data from an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="75b54-140">Procedura: scrivere dati oggetto in un file XMLHow to: Write Object Data to an XML File</span><span class="sxs-lookup"><span data-stu-id="75b54-140">How to: Write Object Data to an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
