---
title: 'Procedura: Leggere da file di testo con valori delimitati da virgole in Visual Basic'
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
- files, parsing
- text files, tasks
- reading text files, comma-delimited
- text files, reading
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
caps.latest.revision: 19
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
ms.openlocfilehash: 2ae6a3f315a8e433386319d1aa1a7f48726a19bb
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-from-comma-delimited-text-files-in-visual-basic"></a><span data-ttu-id="bd29b-102">Procedura: Leggere da file di testo con valori delimitati da virgole in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bd29b-102">How to: read from comma-delimited text files in Visual Basic</span></span>
<span data-ttu-id="bd29b-103">L'oggetto `TextFieldParser` consente di analizzare in modo facile ed efficace i file di testo strutturati, ad esempio i log.</span><span class="sxs-lookup"><span data-stu-id="bd29b-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="bd29b-104">La proprietà `TextFieldType` definisce se si tratta di un file delimitato o di un file con campi di testo a larghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="bd29b-104">The `TextFieldType` property defines whether it is a delimited file or one with fixed-width fields of text.</span></span>  
  
### <a name="to-parse-a-comma-delimited-text-file"></a><span data-ttu-id="bd29b-105">Per analizzare un file di testo con valori delimitati da virgole</span><span class="sxs-lookup"><span data-stu-id="bd29b-105">To parse a comma delimited text file</span></span>  
  
1.  <span data-ttu-id="bd29b-106">Creare un nuovo oggetto `TextFieldParser`.</span><span class="sxs-lookup"><span data-stu-id="bd29b-106">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="bd29b-107">Il codice riportato di seguito crea l'oggetto `TextFieldParser` denominato `MyReader` e apre il file `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="bd29b-107">The following code creates the `TextFieldParser` named `MyReader` and opens the file `test.txt`.</span></span>  
  
     <span data-ttu-id="bd29b-108">[!code-vb[VbFileIORead#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="bd29b-108">[!code-vb[VbFileIORead#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_1.vb)]</span></span>  
  
2.  <span data-ttu-id="bd29b-109">Definire il tipo `TextField` e il delimitatore.</span><span class="sxs-lookup"><span data-stu-id="bd29b-109">Define the `TextField` type and delimiter.</span></span> <span data-ttu-id="bd29b-110">Nel codice riportato di seguito viene definita la proprietà `TextFieldType` come `Delimited` e il delimitatore come ",".</span><span class="sxs-lookup"><span data-stu-id="bd29b-110">The following code defines the `TextFieldType` property as `Delimited` and the delimiter as ",".</span></span>  
  
     <span data-ttu-id="bd29b-111">[!code-vb[VbFileIORead#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="bd29b-111">[!code-vb[VbFileIORead#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_2.vb)]</span></span>  
  
3.  <span data-ttu-id="bd29b-112">Eseguire il ciclo attraverso i campi nel file.</span><span class="sxs-lookup"><span data-stu-id="bd29b-112">Loop through the fields in the file.</span></span> <span data-ttu-id="bd29b-113">Se sono presenti righe danneggiate, segnalare un errore e continuare l'analisi.</span><span class="sxs-lookup"><span data-stu-id="bd29b-113">If any lines are corrupt, report an error and continue parsing.</span></span> <span data-ttu-id="bd29b-114">Nel codice riportato di seguito viene eseguito un ciclo attraverso il file, visualizzando ogni campo e segnalando eventuali campi formattati in modo errato.</span><span class="sxs-lookup"><span data-stu-id="bd29b-114">The following code loops through the file, displaying each field in turn and reporting any fields that are formatted incorrectly.</span></span>  
  
     <span data-ttu-id="bd29b-115">[!code-vb[VbFileIORead#17](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="bd29b-115">[!code-vb[VbFileIORead#17](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_3.vb)]</span></span>  
  
4.  <span data-ttu-id="bd29b-116">Chiudere i blocchi `While` e `Using` con `End While` ed `End Using`.</span><span class="sxs-lookup"><span data-stu-id="bd29b-116">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     <span data-ttu-id="bd29b-117">[!code-vb[VbFileIORead#18](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="bd29b-117">[!code-vb[VbFileIORead#18](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd29b-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="bd29b-118">Example</span></span>  
 <span data-ttu-id="bd29b-119">Nell'esempio riportato di seguito viene letto il file `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="bd29b-119">This example reads from the file `test.txt`.</span></span>  
  
 <span data-ttu-id="bd29b-120">[!code-vb[VbFileIORead#19](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="bd29b-120">[!code-vb[VbFileIORead#19](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_5.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bd29b-121">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="bd29b-121">Robust programming</span></span>  
 <span data-ttu-id="bd29b-122">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="bd29b-122">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="bd29b-123">Impossibile analizzare la riga usando il formato specificato (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="bd29b-123">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="bd29b-124">Il messaggio di eccezione specifica la riga che ha generato l'eccezione, mentre alla proprietà <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> viene assegnato il testo contenuto nella riga.</span><span class="sxs-lookup"><span data-stu-id="bd29b-124">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned the text contained in the line.</span></span>  
  
-   <span data-ttu-id="bd29b-125">File specificato inesistente (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="bd29b-125">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="bd29b-126">Un contesto di attendibilità parziale in cui gli utenti non dispongono di autorizzazioni sufficienti per accedere al file</span><span class="sxs-lookup"><span data-stu-id="bd29b-126">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="bd29b-127">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="bd29b-127">(<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="bd29b-128">Percorso del file troppo lungo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="bd29b-128">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="bd29b-129">L'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="bd29b-129">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd29b-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd29b-130">See also</span></span>  
 <span data-ttu-id="bd29b-131"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bd29b-131"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span></span>   
 <span data-ttu-id="bd29b-132">[Procedura: Leggere da file di testo a larghezza fissa](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="bd29b-132">[How to: Read From Fixed-width Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md) </span></span>  
 <span data-ttu-id="bd29b-133">[Procedura: Leggere da file di testo con più formati](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span><span class="sxs-lookup"><span data-stu-id="bd29b-133">[How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span></span>  
 <span data-ttu-id="bd29b-134">[Analisi dei file di testo con l'oggetto TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md) </span><span class="sxs-lookup"><span data-stu-id="bd29b-134">[Parsing Text Files with the TextFieldParser Object](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md) </span></span>  
 <span data-ttu-id="bd29b-135">[Procedura dettagliata: Modifica di file e directory in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md) </span><span class="sxs-lookup"><span data-stu-id="bd29b-135">[Walkthrough: Manipulating Files and Directories in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md) </span></span>  
 [<span data-ttu-id="bd29b-136">Risoluzione dei problemi: lettura e scrittura nei file di testo</span><span class="sxs-lookup"><span data-stu-id="bd29b-136">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)

