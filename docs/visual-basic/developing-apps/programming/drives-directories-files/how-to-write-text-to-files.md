---
title: 'Procedura: scrivere testo in file in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic]
- examples [Visual Basic], text files
ms.assetid: 304956eb-530d-4df7-b48f-9b4d1f2581a0
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cfdae490a7d78e44f230e22f8431d5ee91461c22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-text-to-files-in-visual-basic"></a><span data-ttu-id="811b4-102">Procedura: scrivere testo in file in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="811b4-102">How to: Write Text to Files in Visual Basic</span></span>
<span data-ttu-id="811b4-103">Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> può essere usato per scrivere testo nei file.</span><span class="sxs-lookup"><span data-stu-id="811b4-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method can be used to write text to files.</span></span> <span data-ttu-id="811b4-104">Se il file specificato non esiste, viene creato.</span><span class="sxs-lookup"><span data-stu-id="811b4-104">If the specified file does not exist, it is created.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="811b4-105">Routine</span><span class="sxs-lookup"><span data-stu-id="811b4-105">Procedure</span></span>  
  
#### <a name="to-write-text-to-a-file"></a><span data-ttu-id="811b4-106">Per scrivere testo in un file</span><span class="sxs-lookup"><span data-stu-id="811b4-106">To write text to a file</span></span>  
  
-   <span data-ttu-id="811b4-107">Usare il metodo `WriteAllText` per scrivere testo in un file, specificando il file e il testo da scrivere.</span><span class="sxs-lookup"><span data-stu-id="811b4-107">Use the `WriteAllText` method to write text to a file, specifying the file and text to be written.</span></span> <span data-ttu-id="811b4-108">In questo esempio la riga `"This is new text."` viene scritta nel file denominato `test.txt`, aggiungendo il nuovo testo al testo eventualmente già esistente nel file.</span><span class="sxs-lookup"><span data-stu-id="811b4-108">This example writes the line `"This is new text."` to the file named `test.txt`, appending the text to any existing text in the file.</span></span>  
  
     [!code-vb[VbFileIOWrite#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_1.vb)]  
  
#### <a name="to-write-a-series-of-strings-to-a-file"></a><span data-ttu-id="811b4-109">Per scrivere una serie di stringhe in un file</span><span class="sxs-lookup"><span data-stu-id="811b4-109">To write a series of strings to a file</span></span>  
  
-   <span data-ttu-id="811b4-110">Scorrere la raccolta di stringhe.</span><span class="sxs-lookup"><span data-stu-id="811b4-110">Loop through the string collection.</span></span> <span data-ttu-id="811b4-111">Usare il metodo `WriteAllText` per scrivere testo in un file, specificando il file di destinazione e la stringa da aggiungere e impostando `append` su `True`.</span><span class="sxs-lookup"><span data-stu-id="811b4-111">Use the `WriteAllText` method to write text to a file, specifying the target file and string to be added and setting `append` to `True`.</span></span>  
  
     <span data-ttu-id="811b4-112">In questo esempio vengono scritti i nomi dei file nella directory `Documents and Settings` in `FileList.txt`, inserendo un ritorno a capo tra ogni nome per una migliore leggibilità.</span><span class="sxs-lookup"><span data-stu-id="811b4-112">This example writes the names of the files in the `Documents and Settings` directory to `FileList.txt`, inserting a carriage return between each for better readability.</span></span>  
  
     [!code-vb[VbFileIOWrite#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_2.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="811b4-113">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="811b4-113">Robust Programming</span></span>  
 <span data-ttu-id="811b4-114">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="811b4-114">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="811b4-115">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="811b4-115">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="811b4-116">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="811b4-116">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="811b4-117">`File` punta a un percorso che non esiste (<xref:System.IO.FileNotFoundException> o <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="811b4-117">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="811b4-118">Il file è in uso in un altro processo oppure si verifica un errore di I/O (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="811b4-118">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="811b4-119">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="811b4-119">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="811b4-120">Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="811b4-120">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="811b4-121">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="811b4-121">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="811b4-122">Il disco è pieno e la chiamata a `WriteAllText` ha esito negativo (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="811b4-122">The disk is full, and the call to `WriteAllText` fails (<xref:System.IO.IOException>).</span></span>  
  
 <span data-ttu-id="811b4-123">Se eseguito in un contesto ad attendibilità parziale, il codice potrebbe generare un'eccezione a causa dell'insufficienza di privilegi.</span><span class="sxs-lookup"><span data-stu-id="811b4-123">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="811b4-124">Per altre informazioni, vedere [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8) (Nozioni di base sulla sicurezza dell'accesso di codice).</span><span class="sxs-lookup"><span data-stu-id="811b4-124">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="811b4-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="811b4-125">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>  
 [<span data-ttu-id="811b4-126">Procedura: leggere da file di testo</span><span class="sxs-lookup"><span data-stu-id="811b4-126">How to: Read from Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)
