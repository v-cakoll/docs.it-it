---
title: 'Procedura: Leggere da file binari in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- binary files [Visual Basic], reading from
- I/O [Visual Basic], reading from binary files
- ReadAllBytes method [Visual Basic], reading from binary files
- My.Computer.FileSystem object, reading from binary files
ms.assetid: d2b1269e-24b6-42e0-9414-ae708db282d8
ms.openlocfilehash: 6594bd8180688ae453534207170a4befc96c5c37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647621"
---
# <a name="how-to-read-from-binary-files-in-visual-basic"></a><span data-ttu-id="43bfe-102">Procedura: Leggere da file binari in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="43bfe-102">How to: Read From Binary Files in Visual Basic</span></span>
<span data-ttu-id="43bfe-103">L'oggetto `My.Computer.FileSystem` offre il metodo `ReadAllBytes` per leggere da file binari.</span><span class="sxs-lookup"><span data-stu-id="43bfe-103">The `My.Computer.FileSystem` object provides the `ReadAllBytes` method for reading from binary files.</span></span>  
  
### <a name="to-read-from-a-binary-file"></a><span data-ttu-id="43bfe-104">Per leggere da un file binario</span><span class="sxs-lookup"><span data-stu-id="43bfe-104">To read from a binary file</span></span>  
  
-   <span data-ttu-id="43bfe-105">Usare il metodo `ReadAllBytes` che restituisce il contenuto di un file sotto forma di matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="43bfe-105">Use the `ReadAllBytes` method, which returns the contents of a file as a byte array.</span></span> <span data-ttu-id="43bfe-106">Nell'esempio riportato di seguito viene letto il file `C:/Documents and Settings/selfportrait.jpg`.</span><span class="sxs-lookup"><span data-stu-id="43bfe-106">This example reads from the file `C:/Documents and Settings/selfportrait.jpg`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#78](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_1.vb)]  
  
-   <span data-ttu-id="43bfe-107">Per file binari di grandi dimensioni, è possibile usare il metodo <xref:System.IO.FileStream.Read%2A> dell'oggetto <xref:System.IO.FileStream> per leggere solo una parte specificata del file per volta.</span><span class="sxs-lookup"><span data-stu-id="43bfe-107">For large binary files, you can use the <xref:System.IO.FileStream.Read%2A> method of the <xref:System.IO.FileStream> object to read from the file only a specified amount at a time.</span></span> <span data-ttu-id="43bfe-108">È quindi possibile limitare la parte del file caricata nella memoria per ogni operazione di lettura.</span><span class="sxs-lookup"><span data-stu-id="43bfe-108">You can then limit how much of the file is loaded into memory for each read operation.</span></span> <span data-ttu-id="43bfe-109">Nell'esempio di codice seguente viene copiato un file e viene consentito al chiamante di specificare la parte di file letta nella memoria per l'operazione di lettura.</span><span class="sxs-lookup"><span data-stu-id="43bfe-109">The following code example copies a file and allows the caller to specify how much of the file is read into memory per read operation.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#91](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_2.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="43bfe-110">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="43bfe-110">Robust Programming</span></span>  
 <span data-ttu-id="43bfe-111">Le condizioni seguenti possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="43bfe-111">The following conditions may cause an exception to be thrown:</span></span>  
  
-   <span data-ttu-id="43bfe-112">Il percorso non è valido per uno dei seguenti motivi: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di una periferica (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="43bfe-112">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="43bfe-113">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="43bfe-113">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="43bfe-114">Il file non esiste (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="43bfe-114">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="43bfe-115">Il file è in uso in un altro processo oppure si verifica un errore di I/O (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="43bfe-115">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="43bfe-116">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="43bfe-116">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="43bfe-117">Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="43bfe-117">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="43bfe-118">La memoria disponibile non è sufficiente per la scrittura della stringa nel buffer (<xref:System.OutOfMemoryException>).</span><span class="sxs-lookup"><span data-stu-id="43bfe-118">There is not enough memory to write the string to buffer (<xref:System.OutOfMemoryException>).</span></span>  
  
-   <span data-ttu-id="43bfe-119">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="43bfe-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
 <span data-ttu-id="43bfe-120">Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="43bfe-120">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="43bfe-121">È possibile ad esempio che il file Form1.vb non sia un file di origine di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="43bfe-121">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
 <span data-ttu-id="43bfe-122">Prima di usare i dati nell'applicazione verificare tutti gli input.</span><span class="sxs-lookup"><span data-stu-id="43bfe-122">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="43bfe-123">È possibile che il contenuto del file non corrisponda a quanto previsto e che quindi i metodi per la lettura dal file non abbiano esito positivo.</span><span class="sxs-lookup"><span data-stu-id="43bfe-123">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43bfe-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43bfe-124">See also</span></span>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [<span data-ttu-id="43bfe-125">Lettura da file</span><span class="sxs-lookup"><span data-stu-id="43bfe-125">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="43bfe-126">Procedura: Leggere da file di testo con più formati</span><span class="sxs-lookup"><span data-stu-id="43bfe-126">How to: Read From Text Files with Multiple Formats</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="43bfe-127">Archiviazione e lettura di dati negli Appunti</span><span class="sxs-lookup"><span data-stu-id="43bfe-127">Storing Data to and Reading from the Clipboard</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md)
