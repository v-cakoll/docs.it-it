---
title: Archiviazione e lettura di dati negli Appunti (Visual Basic)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Clipboard, storing data to (My.Computer.Clipboard)
- Clipboard, reading from (My.Computer.Clipboard)
- Clipboard
- My.Computer.Clipboard object, tasks
- data [Visual Basic], Clipboard
- reading data, from Clipboard
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3b60942cf3e3a7f588a7838bcae0cb7b6fae2278
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a><span data-ttu-id="c232c-102">Archiviazione e lettura di dati negli Appunti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c232c-102">Storing data to and reading from the Clipboard (Visual Basic)</span></span>
<span data-ttu-id="c232c-103">Gli Appunti possono essere usati per archiviare i dati, ad esempio testo e immagini.</span><span class="sxs-lookup"><span data-stu-id="c232c-103">The Clipboard can be used to store data, such as text and images.</span></span> <span data-ttu-id="c232c-104">Poiché gli Appunti sono condivisi tra tutti i processi attivi, possono essere usati per trasferire dati tra di essi.</span><span class="sxs-lookup"><span data-stu-id="c232c-104">Because the Clipboard is shared by all active processes, it can be used to transfer data between them.</span></span> <span data-ttu-id="c232c-105">L'oggetto `My.Computer.Clipboard` consente di accedere facilmente agli Appunti per leggere e scrivere.</span><span class="sxs-lookup"><span data-stu-id="c232c-105">The `My.Computer.Clipboard` object allows you to easily access the Clipboard and to read from and write to it.</span></span>  
  
## <a name="reading-from-the-clipboard"></a><span data-ttu-id="c232c-106">Lettura dagli Appunti</span><span class="sxs-lookup"><span data-stu-id="c232c-106">Reading from the Clipboard</span></span>  
 <span data-ttu-id="c232c-107">Usare il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> per leggere il testo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="c232c-107">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> method to read the text in the Clipboard.</span></span> <span data-ttu-id="c232c-108">Il codice seguente legge il testo e lo visualizza in una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="c232c-108">The following code reads the text and displays it in a message box.</span></span> <span data-ttu-id="c232c-109">Per far funzionare l'esempio, gli Appunti devono contenere testo archiviato.</span><span class="sxs-lookup"><span data-stu-id="c232c-109">There must be text stored on the Clipboard for the example to run correctly.</span></span>  
  
 <span data-ttu-id="c232c-110">[!code-vb[VbVbcnMyClipboard#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c232c-110">[!code-vb[VbVbcnMyClipboard#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_1.vb)]</span></span>  
  
 <span data-ttu-id="c232c-111">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="c232c-111">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="c232c-112">Nello strumento di selezione dei frammenti di codice il frammento di codice si trova in **Applicazioni Windows Form > Appunti**.</span><span class="sxs-lookup"><span data-stu-id="c232c-112">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.</span></span> <span data-ttu-id="c232c-113">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="c232c-113">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="c232c-114">Usare il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> per recuperare un'immagine dagli Appunti.</span><span class="sxs-lookup"><span data-stu-id="c232c-114">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> method to retrieve an image from the Clipboard.</span></span> <span data-ttu-id="c232c-115">Questo esempio verifica se è disponibile un'immagine negli Appunti prima di tentarne il recupero e assegnarlo a `PictureBox1`.</span><span class="sxs-lookup"><span data-stu-id="c232c-115">This example checks to see if there is an image on the Clipboard before retrieving it and assigning it to `PictureBox1`.</span></span>  
  
 <span data-ttu-id="c232c-116">[!code-vb[VbResourceTasks#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c232c-116">[!code-vb[VbResourceTasks#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_2.vb)]</span></span>  
  
 <span data-ttu-id="c232c-117">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="c232c-117">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="c232c-118">Nello strumento di selezione dei frammenti di codice il frammento di codice si trova in **Applicazioni Windows Form > Appunti**. Per altre informazioni, vedere [Frammenti di codice](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="c232c-118">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="c232c-119">Gli elementi inseriti negli Appunti verranno mantenuti anche dopo l'arresto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c232c-119">Items placed on the Clipboard will persist even after the application is shut down.</span></span>  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a><span data-ttu-id="c232c-120">Determinazione del tipo di file archiviati negli Appunti</span><span class="sxs-lookup"><span data-stu-id="c232c-120">Determining the type of file stored in the Clipboard</span></span>  
 <span data-ttu-id="c232c-121">I dati contenuti negli Appunti potrebbero avere diverse forme, ad esempio testo, file audio o immagine.</span><span class="sxs-lookup"><span data-stu-id="c232c-121">Data on the Clipboard may take a number of different forms, such as text, an audio file, or an image.</span></span> <span data-ttu-id="c232c-122">Per determinare il tipo di file negli Appunti, è possibile usare metodi quali <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> e <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.</span><span class="sxs-lookup"><span data-stu-id="c232c-122">In order to determine what sort of file is on the Clipboard, you can use methods such as <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A>, and <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.</span></span> <span data-ttu-id="c232c-123">Il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> può essere usato nel caso in cui si voglia controllare un formato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c232c-123">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> method can be used if you have a custom format that you want to check.</span></span>  
  
 <span data-ttu-id="c232c-124">Usare la funzione `ContainsImage` per determinare se i dati contenuti negli Appunti costituiscono un'immagine.</span><span class="sxs-lookup"><span data-stu-id="c232c-124">Use the `ContainsImage` function to determine whether the data contained on the Clipboard is an image.</span></span> <span data-ttu-id="c232c-125">Il codice seguente consente di controllare se i dati costituiscono un'immagine e invia una segnalazione in merito.</span><span class="sxs-lookup"><span data-stu-id="c232c-125">The following code checks to see whether the data is an image and reports accordingly.</span></span>  
  
 <span data-ttu-id="c232c-126">[!code-vb[VbResourceTasks#13](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="c232c-126">[!code-vb[VbResourceTasks#13](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_3.vb)]</span></span>  
  
## <a name="clearing-the-clipboard"></a><span data-ttu-id="c232c-127">Cancellazione degli Appunti</span><span class="sxs-lookup"><span data-stu-id="c232c-127">Clearing the Clipboard</span></span>  
 <span data-ttu-id="c232c-128">Il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> cancella il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="c232c-128">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> method clears the Clipboard.</span></span> <span data-ttu-id="c232c-129">Poiché gli Appunti sono condivisi da altri processi, la cancellazione può avere conseguenze su tali processi.</span><span class="sxs-lookup"><span data-stu-id="c232c-129">Because the Clipboard is shared by other processes, clearing it may have an impact on those processes.</span></span>  
  
 <span data-ttu-id="c232c-130">Nell'esempio di codice seguente viene illustrato come utilizzare il metodo `Clear`.</span><span class="sxs-lookup"><span data-stu-id="c232c-130">The following code shows how to use the `Clear` method.</span></span>  
  
 <span data-ttu-id="c232c-131">[!code-vb[VbVbcnMyClipboard#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="c232c-131">[!code-vb[VbVbcnMyClipboard#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_4.vb)]</span></span>  
  
## <a name="writing-to-the-clipboard"></a><span data-ttu-id="c232c-132">Scrittura negli Appunti</span><span class="sxs-lookup"><span data-stu-id="c232c-132">Writing to the Clipboard</span></span>  
 <span data-ttu-id="c232c-133">Usare il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> per scrivere testo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="c232c-133">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> method to write text to the Clipboard.</span></span> <span data-ttu-id="c232c-134">Il codice seguente scrive la stringa "Questa è una stringa di prova" negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="c232c-134">The following code writes the string "This is a test string" to the Clipboard.</span></span>  
  
 <span data-ttu-id="c232c-135">[!code-vb[VbVbcnMyClipboard#1](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="c232c-135">[!code-vb[VbVbcnMyClipboard#1](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_5.vb)]</span></span>  
  
 <span data-ttu-id="c232c-136">Il metodo `SetText` può accettare un parametro di formato contenente un tipo di <xref:System.Windows.Forms.TextDataFormat>.</span><span class="sxs-lookup"><span data-stu-id="c232c-136">The `SetText` method can accept a format parameter that contains a type of <xref:System.Windows.Forms.TextDataFormat>.</span></span> <span data-ttu-id="c232c-137">Il codice seguente scrive la stringa "Questa è una stringa di prova" negli Appunti come testo RTF.</span><span class="sxs-lookup"><span data-stu-id="c232c-137">The following code writes the string "This is a test string" to the Clipboard as RTF text.</span></span>  
  
 <span data-ttu-id="c232c-138">[!code-vb[VbVbcnMyClipboard#2](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="c232c-138">[!code-vb[VbVbcnMyClipboard#2](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_6.vb)]</span></span>  
  
 <span data-ttu-id="c232c-139">Usare il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> per scrivere dati negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="c232c-139">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> method to write data to the Clipboard.</span></span> <span data-ttu-id="c232c-140">In questo esempio `DataObject``dataChunk` viene scritto negli Appunti nel formato personalizzato `specialFormat`.</span><span class="sxs-lookup"><span data-stu-id="c232c-140">This example writes the `DataObject``dataChunk` to the Clipboard in the custom format `specialFormat`.</span></span>  
  
 <span data-ttu-id="c232c-141">[!code-vb[VbVbcnMyClipboard#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="c232c-141">[!code-vb[VbVbcnMyClipboard#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_7.vb)]</span></span>  
  
 <span data-ttu-id="c232c-142">Usare il metodo <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> per scrivere dati audio negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="c232c-142">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> method to write audio data to the Clipboard.</span></span> <span data-ttu-id="c232c-143">Questo esempio crea la matrice di byte `musicReader`, legge il file `cool.wav` al suo interno e lo scrive quindi negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="c232c-143">This example creates the byte array `musicReader`, reads the file `cool.wav` into it, and then writes it to the Clipboard.</span></span>  
  
 <span data-ttu-id="c232c-144">[!code-vb[VbResourceTasks#5](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="c232c-144">[!code-vb[VbResourceTasks#5](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_8.vb)]</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c232c-145">Dal momento che gli Appunti sono accessibili da altri utenti, non usarli per archiviare informazioni sensibili, ad esempio password o dati riservati.</span><span class="sxs-lookup"><span data-stu-id="c232c-145">Because the Clipboard can be accessed by other users, do not use it to store sensitive information, such as passwords or confidential data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c232c-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c232c-146">See also</span></span>  
 <span data-ttu-id="c232c-147"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy></span><span class="sxs-lookup"><span data-stu-id="c232c-147"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy></span></span>   
 <span data-ttu-id="c232c-148"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A></span><span class="sxs-lookup"><span data-stu-id="c232c-148"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A></span></span>   
 <span data-ttu-id="c232c-149"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A></span><span class="sxs-lookup"><span data-stu-id="c232c-149"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A></span></span>   
 <span data-ttu-id="c232c-150">[Procedura: Leggere dati oggetto in un file XML](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md) </span><span class="sxs-lookup"><span data-stu-id="c232c-150">[How to: Read Object Data from an XML File](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md) </span></span>  
 [<span data-ttu-id="c232c-151">Procedura: Scrivere dati oggetto in un file XML</span><span class="sxs-lookup"><span data-stu-id="c232c-151">How to: Write Object Data to an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)

