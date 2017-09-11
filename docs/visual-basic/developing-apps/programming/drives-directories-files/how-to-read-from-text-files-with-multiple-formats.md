---
title: "Procedura: leggere file di testo con più formati in Visual Basic"
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
- TextFieldParser object, reading from a file
- TextFieldType enumeration
- My.Computer.FileSystem.WriteAllText method, parsing structured text files
- WriteAllText method, parsing structured text files
- PeekChars method, determining format of text
- reading text files, multiple formats
- I/O [Visual Basic], reading text files
- text files, reading
ms.assetid: 8d185eb2-79ca-42cd-95a7-d3ff44a5a0f8
caps.latest.revision: 17
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
ms.openlocfilehash: be085e5a0f7a57890893ba310db3c66480b300da
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-from-text-files-with-multiple-formats-in-visual-basic"></a><span data-ttu-id="836b5-102">Procedura: leggere file di testo con più formati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="836b5-102">How to: Read From Text Files with Multiple Formats in Visual Basic</span></span>
<span data-ttu-id="836b5-103">L'oggetto <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> consente di analizzare in modo facile ed efficace i file di testo strutturati, ad esempio i log.</span><span class="sxs-lookup"><span data-stu-id="836b5-103">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="836b5-104">È possibile elaborare un file con più formati usando il metodo `PeekChars` per determinare il formato di ogni riga durante l'analisi del file.</span><span class="sxs-lookup"><span data-stu-id="836b5-104">You can process a file with multiple formats by using the `PeekChars` method to determine the format of each line as you parse through the file.</span></span>  
  
### <a name="to-parse-a-text-file-with-multiple-formats"></a><span data-ttu-id="836b5-105">Per analizzare un file di testo con più formati</span><span class="sxs-lookup"><span data-stu-id="836b5-105">To parse a text file with multiple formats</span></span>  
  
1.  <span data-ttu-id="836b5-106">Aggiungere un file di testo denominato testfile.txt al progetto.</span><span class="sxs-lookup"><span data-stu-id="836b5-106">Add a text file named testfile.txt to your project.</span></span> <span data-ttu-id="836b5-107">Aggiungere quanto segue al file di testo.</span><span class="sxs-lookup"><span data-stu-id="836b5-107">Add the following content to the text file.</span></span>  
  
    ```  
    Err  1001 Cannot access resource.  
    Err  2014 Resource not found.  
    Acc  10/03/2009User1      Administrator.  
    Err  0323 Warning: Invalid access attempt.  
    Acc  10/03/2009User2      Standard user.  
    Acc  10/04/2009User2      Standard user.  
    ```  
  
2.  <span data-ttu-id="836b5-108">Definire il formato previsto e il formato usato al momento della segnalazione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="836b5-108">Define the expected format and the format used when an error is reported.</span></span> <span data-ttu-id="836b5-109">L'ultima voce in ogni matrice è -1, pertanto si presuppone che l'ultimo campo sia di larghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="836b5-109">The last entry in each array is -1, therefore the last field is assumed to be of variable width.</span></span> <span data-ttu-id="836b5-110">Tale occorrenza si verifica quando l'ultima voce nella matrice è minore o uguale a 0.</span><span class="sxs-lookup"><span data-stu-id="836b5-110">This occurs when the last entry in the array is less than or equal to 0.</span></span>  
  
     <span data-ttu-id="836b5-111">[!code-vb[VbFileIORead#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="836b5-111">[!code-vb[VbFileIORead#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_1.vb)]</span></span>  
  
3.  <span data-ttu-id="836b5-112">Creare un nuovo oggetto <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>, specificando la larghezza e il formato.</span><span class="sxs-lookup"><span data-stu-id="836b5-112">Create a new <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object, defining the width and format.</span></span>  
  
     <span data-ttu-id="836b5-113">[!code-vb[VbFileIORead#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="836b5-113">[!code-vb[VbFileIORead#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_2.vb)]</span></span>  
  
4.  <span data-ttu-id="836b5-114">Scorrere le righe, verificando il formato prima della lettura.</span><span class="sxs-lookup"><span data-stu-id="836b5-114">Loop through the rows, testing for format before reading.</span></span>  
  
     <span data-ttu-id="836b5-115">[!code-vb[VbFileIORead#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="836b5-115">[!code-vb[VbFileIORead#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_3.vb)]</span></span>  
  
5.  <span data-ttu-id="836b5-116">Scrivere gli errori nella console.</span><span class="sxs-lookup"><span data-stu-id="836b5-116">Write errors to the console.</span></span>  
  
     <span data-ttu-id="836b5-117">[!code-vb[VbFileIORead#7](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="836b5-117">[!code-vb[VbFileIORead#7](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="836b5-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="836b5-118">Example</span></span>  
 <span data-ttu-id="836b5-119">Di seguito è riportato l'esempio completo di lettura dal file `testfile.txt`.</span><span class="sxs-lookup"><span data-stu-id="836b5-119">Following is the complete example that reads from the file `testfile.txt`.</span></span>  
  
 <span data-ttu-id="836b5-120">[!code-vb[VbFileIORead#8](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="836b5-120">[!code-vb[VbFileIORead#8](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_5.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="836b5-121">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="836b5-121">Robust Programming</span></span>  
 <span data-ttu-id="836b5-122">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="836b5-122">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="836b5-123">Impossibile analizzare la riga usando il formato specificato (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="836b5-123">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="836b5-124">Il messaggio di eccezione specifica la riga che ha generato l'eccezione, mentre alla proprietà <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> viene assegnato il testo contenuto nella riga.</span><span class="sxs-lookup"><span data-stu-id="836b5-124">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned to the text contained in the line.</span></span>  
  
-   <span data-ttu-id="836b5-125">File specificato inesistente (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="836b5-125">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="836b5-126">Un contesto di attendibilità parziale in cui gli utenti non dispongono di autorizzazioni sufficienti per accedere al file</span><span class="sxs-lookup"><span data-stu-id="836b5-126">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="836b5-127">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="836b5-127">(<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="836b5-128">Percorso del file troppo lungo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="836b5-128">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="836b5-129">L'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="836b5-129">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="836b5-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="836b5-130">See Also</span></span>  
 <span data-ttu-id="836b5-131"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="836b5-131"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span></span>   
 <span data-ttu-id="836b5-132"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A></span><span class="sxs-lookup"><span data-stu-id="836b5-132"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A></span></span>   
 <span data-ttu-id="836b5-133"><xref:Microsoft.VisualBasic.FileIO.MalformedLineException></span><span class="sxs-lookup"><span data-stu-id="836b5-133"><xref:Microsoft.VisualBasic.FileIO.MalformedLineException></span></span>   
 <span data-ttu-id="836b5-134"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A></span><span class="sxs-lookup"><span data-stu-id="836b5-134"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A></span></span>   
 <span data-ttu-id="836b5-135"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A></span><span class="sxs-lookup"><span data-stu-id="836b5-135"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A></span></span>   
 <span data-ttu-id="836b5-136"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A></span><span class="sxs-lookup"><span data-stu-id="836b5-136"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A></span></span>   
 <span data-ttu-id="836b5-137">[Procedura: Leggere da file di testo con valori delimitati da virgole](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="836b5-137">[How to: Read From Comma-Delimited Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md) </span></span>  
 <span data-ttu-id="836b5-138">[Procedura: Leggere da file di testo a larghezza fissa](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="836b5-138">[How to: Read From Fixed-width Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md) </span></span>  
 [<span data-ttu-id="836b5-139">Analisi dei file di testo con l'oggetto TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="836b5-139">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)

