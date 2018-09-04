---
title: Archiviazione e lettura di dati negli Appunti (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Clipboard, storing data to (My.Computer.Clipboard)
- Clipboard, reading from (My.Computer.Clipboard)
- Clipboard
- My.Computer.Clipboard object, tasks
- data [Visual Basic], Clipboard
- reading data, from Clipboard
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
ms.openlocfilehash: 7964a39bb84ac6af6b6c196c053f51c30301985c
ms.sourcegitcommit: 8c6c62ba1eefa492701e264e41890ee20fae77a3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2018
ms.locfileid: "42792349"
---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a><span data-ttu-id="4349c-102">Archiviazione e lettura di dati negli Appunti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4349c-102">Storing data to and reading from the Clipboard (Visual Basic)</span></span>
<span data-ttu-id="4349c-103">Gli Appunti possono essere usati per archiviare i dati, ad esempio testo e immagini.</span><span class="sxs-lookup"><span data-stu-id="4349c-103">The Clipboard can be used to store data, such as text and images.</span></span> <span data-ttu-id="4349c-104">Poiché gli Appunti sono condivisi tra tutti i processi attivi, possono essere usati per trasferire dati tra di essi.</span><span class="sxs-lookup"><span data-stu-id="4349c-104">Because the Clipboard is shared by all active processes, it can be used to transfer data between them.</span></span> <span data-ttu-id="4349c-105">L'oggetto `My.Computer.Clipboard` consente di accedere facilmente agli Appunti per leggere e scrivere.</span><span class="sxs-lookup"><span data-stu-id="4349c-105">The `My.Computer.Clipboard` object allows you to easily access the Clipboard and to read from and write to it.</span></span>  
  
## <a name="reading-from-the-clipboard"></a><span data-ttu-id="4349c-106">Lettura dagli Appunti</span><span class="sxs-lookup"><span data-stu-id="4349c-106">Reading from the Clipboard</span></span>  
 <span data-ttu-id="4349c-107">Usare il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> per leggere il testo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="4349c-107">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> method to read the text in the Clipboard.</span></span> <span data-ttu-id="4349c-108">Il codice seguente legge il testo e lo visualizza in una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="4349c-108">The following code reads the text and displays it in a message box.</span></span> <span data-ttu-id="4349c-109">Per far funzionare l'esempio, gli Appunti devono contenere testo archiviato.</span><span class="sxs-lookup"><span data-stu-id="4349c-109">There must be text stored on the Clipboard for the example to run correctly.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_1.vb)]  
  
 <span data-ttu-id="4349c-110">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4349c-110">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="4349c-111">Nello strumento di selezione dei frammenti di codice il frammento di codice si trova in **Applicazioni Windows Form > Appunti**.</span><span class="sxs-lookup"><span data-stu-id="4349c-111">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.</span></span> <span data-ttu-id="4349c-112">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="4349c-112">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="4349c-113">Usare il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> per recuperare un'immagine dagli Appunti.</span><span class="sxs-lookup"><span data-stu-id="4349c-113">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> method to retrieve an image from the Clipboard.</span></span> <span data-ttu-id="4349c-114">Questo esempio verifica se è disponibile un'immagine negli Appunti prima di tentarne il recupero e assegnarlo a `PictureBox1`.</span><span class="sxs-lookup"><span data-stu-id="4349c-114">This example checks to see if there is an image on the Clipboard before retrieving it and assigning it to `PictureBox1`.</span></span>  
  
 [!code-vb[VbResourceTasks#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_2.vb)]  
  
 <span data-ttu-id="4349c-115">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4349c-115">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="4349c-116">Nello strumento di selezione dei frammenti di codice il frammento di codice si trova in **Applicazioni Windows Form > Appunti**. Per altre informazioni, vedere [Frammenti di codice](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="4349c-116">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="4349c-117">Gli elementi inseriti negli Appunti verranno mantenuti anche dopo l'arresto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4349c-117">Items placed on the Clipboard will persist even after the application is shut down.</span></span>  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a><span data-ttu-id="4349c-118">Determinazione del tipo di file archiviati negli Appunti</span><span class="sxs-lookup"><span data-stu-id="4349c-118">Determining the type of file stored in the Clipboard</span></span>  
 <span data-ttu-id="4349c-119">I dati contenuti negli Appunti potrebbero avere diverse forme, ad esempio testo, file audio o immagine.</span><span class="sxs-lookup"><span data-stu-id="4349c-119">Data on the Clipboard may take a number of different forms, such as text, an audio file, or an image.</span></span> <span data-ttu-id="4349c-120">Per determinare il tipo di file negli Appunti, è possibile usare metodi quali <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> e <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.</span><span class="sxs-lookup"><span data-stu-id="4349c-120">In order to determine what sort of file is on the Clipboard, you can use methods such as <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A>, and <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.</span></span> <span data-ttu-id="4349c-121">Il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> può essere usato nel caso in cui si voglia controllare un formato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4349c-121">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> method can be used if you have a custom format that you want to check.</span></span>  
  
 <span data-ttu-id="4349c-122">Usare la funzione `ContainsImage` per determinare se i dati contenuti negli Appunti costituiscono un'immagine.</span><span class="sxs-lookup"><span data-stu-id="4349c-122">Use the `ContainsImage` function to determine whether the data contained on the Clipboard is an image.</span></span> <span data-ttu-id="4349c-123">Il codice seguente consente di controllare se i dati costituiscono un'immagine e invia una segnalazione in merito.</span><span class="sxs-lookup"><span data-stu-id="4349c-123">The following code checks to see whether the data is an image and reports accordingly.</span></span>  
  
 [!code-vb[VbResourceTasks#13](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_3.vb)]  
  
## <a name="clearing-the-clipboard"></a><span data-ttu-id="4349c-124">Cancellazione degli Appunti</span><span class="sxs-lookup"><span data-stu-id="4349c-124">Clearing the Clipboard</span></span>  
 <span data-ttu-id="4349c-125">Il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> cancella il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="4349c-125">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> method clears the Clipboard.</span></span> <span data-ttu-id="4349c-126">Poiché gli Appunti sono condivisi da altri processi, la cancellazione può avere conseguenze su tali processi.</span><span class="sxs-lookup"><span data-stu-id="4349c-126">Because the Clipboard is shared by other processes, clearing it may have an impact on those processes.</span></span>  
  
 <span data-ttu-id="4349c-127">Nell'esempio di codice seguente viene illustrato come utilizzare il metodo `Clear`.</span><span class="sxs-lookup"><span data-stu-id="4349c-127">The following code shows how to use the `Clear` method.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_4.vb)]  
  
## <a name="writing-to-the-clipboard"></a><span data-ttu-id="4349c-128">Scrittura negli Appunti</span><span class="sxs-lookup"><span data-stu-id="4349c-128">Writing to the Clipboard</span></span>  
 <span data-ttu-id="4349c-129">Usare il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> per scrivere testo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="4349c-129">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> method to write text to the Clipboard.</span></span> <span data-ttu-id="4349c-130">Il codice seguente scrive la stringa "Questa è una stringa di prova" negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="4349c-130">The following code writes the string "This is a test string" to the Clipboard.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#1](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_5.vb)]  
  
 <span data-ttu-id="4349c-131">Il metodo `SetText` può accettare un parametro di formato contenente un tipo di <xref:System.Windows.Forms.TextDataFormat>.</span><span class="sxs-lookup"><span data-stu-id="4349c-131">The `SetText` method can accept a format parameter that contains a type of <xref:System.Windows.Forms.TextDataFormat>.</span></span> <span data-ttu-id="4349c-132">Il codice seguente scrive la stringa "Questa è una stringa di prova" negli Appunti come testo RTF.</span><span class="sxs-lookup"><span data-stu-id="4349c-132">The following code writes the string "This is a test string" to the Clipboard as RTF text.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#2](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_6.vb)]  
  
 <span data-ttu-id="4349c-133">Usare il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> per scrivere dati negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="4349c-133">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> method to write data to the Clipboard.</span></span> <span data-ttu-id="4349c-134">In questo esempio `DataObject` `dataChunk` viene scritto negli Appunti nel formato personalizzato `specialFormat`.</span><span class="sxs-lookup"><span data-stu-id="4349c-134">This example writes the `DataObject` `dataChunk` to the Clipboard in the custom format `specialFormat`.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_7.vb)]  
  
 <span data-ttu-id="4349c-135">Usare il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> per scrivere dati audio negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="4349c-135">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> method to write audio data to the Clipboard.</span></span> <span data-ttu-id="4349c-136">Questo esempio crea la matrice di byte `musicReader`, legge il file `cool.wav` al suo interno e lo scrive quindi negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="4349c-136">This example creates the byte array `musicReader`, reads the file `cool.wav` into it, and then writes it to the Clipboard.</span></span>  
  
 [!code-vb[VbResourceTasks#5](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_8.vb)]  
  
> [!IMPORTANT]
>  <span data-ttu-id="4349c-137">Dal momento che gli Appunti sono accessibili da altri utenti, non usarli per archiviare informazioni sensibili, ad esempio password o dati riservati.</span><span class="sxs-lookup"><span data-stu-id="4349c-137">Because the Clipboard can be accessed by other users, do not use it to store sensitive information, such as passwords or confidential data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4349c-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4349c-138">See also</span></span>  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>  
 [<span data-ttu-id="4349c-139">Procedura: Leggere dati oggetto in un file XML</span><span class="sxs-lookup"><span data-stu-id="4349c-139">How to: Read Object Data from an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)  
 [<span data-ttu-id="4349c-140">Procedura: Scrivere dati oggetto in un file XML</span><span class="sxs-lookup"><span data-stu-id="4349c-140">How to: Write Object Data to an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
