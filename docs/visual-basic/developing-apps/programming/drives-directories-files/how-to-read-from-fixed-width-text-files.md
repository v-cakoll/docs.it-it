---
title: 'Procedura: Leggere da file di testo a larghezza fissa in Visual Basic'
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
- fixed-width text file
- reading text files, fixed-width
- files, parsing
- text files, tasks
- text files, reading
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
caps.latest.revision: 24
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
ms.openlocfilehash: fc45c6d6e4301b2786fefe947ed011ca95f8a79c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-from-fixed-width-text-files-in-visual-basic"></a><span data-ttu-id="f3780-102">Procedura: Leggere da file di testo a larghezza fissa in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3780-102">How to: read from fixed-width text files in Visual Basic</span></span>
<span data-ttu-id="f3780-103">L'oggetto `TextFieldParser` consente di analizzare in modo facile ed efficace i file di testo strutturati, ad esempio i log.</span><span class="sxs-lookup"><span data-stu-id="f3780-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span>  
  
 <span data-ttu-id="f3780-104">La proprietà `TextFieldType` definisce se il file analizzato è un file delimitato o un file con campi di testo a larghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="f3780-104">The `TextFieldType` property defines whether the parsed file is a delimited file or one that has fixed-width fields of text.</span></span> <span data-ttu-id="f3780-105">In un file di testo a larghezza fissa il campo alla fine può avere una larghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="f3780-105">In a fixed-width text file, the field at the end can have a variable width.</span></span> <span data-ttu-id="f3780-106">Per specificare che il campo alla fine deve avere una larghezza variabile, definirlo in modo che abbia una larghezza minore o uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="f3780-106">To specify that the field at the end has a variable width, define it to have a width less than or equal to zero.</span></span>  
  
### <a name="to-parse-a-fixed-width-text-file"></a><span data-ttu-id="f3780-107">Per analizzare un file di testo a larghezza fissa</span><span class="sxs-lookup"><span data-stu-id="f3780-107">To parse a fixed-width text file</span></span>  
  
1.  <span data-ttu-id="f3780-108">Creare un nuovo oggetto `TextFieldParser`.</span><span class="sxs-lookup"><span data-stu-id="f3780-108">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="f3780-109">Il codice riportato di seguito crea l'oggetto `TextFieldParser` denominato `Reader` e apre il file `test.log`.</span><span class="sxs-lookup"><span data-stu-id="f3780-109">The following code creates the `TextFieldParser` named `Reader` and opens the file `test.log`.</span></span>  
  
     <span data-ttu-id="f3780-110">[!code-vb[VbFileIORead#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3780-110">[!code-vb[VbFileIORead#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_1.vb)]</span></span>  
  
2.  <span data-ttu-id="f3780-111">Definire la proprietà `TextFieldType` come `FixedWidth`, impostandone la larghezza e il formato.</span><span class="sxs-lookup"><span data-stu-id="f3780-111">Define the `TextFieldType` property as `FixedWidth`, defining the width and format.</span></span> <span data-ttu-id="f3780-112">Il codice seguente definisce le colonne di testo: la prima ha una larghezza di 5 caratteri, la seconda di 10 e la terza di 11, mentre la quarta ha una larghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="f3780-112">The following code defines the columns of text; the first is 5 characters wide, the second 10, the third 11, and the fourth is of variable width.</span></span>  
  
     <span data-ttu-id="f3780-113">[!code-vb[VbFileIORead#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3780-113">[!code-vb[VbFileIORead#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_2.vb)]</span></span>  
  
3.  <span data-ttu-id="f3780-114">Eseguire il ciclo attraverso i campi nel file.</span><span class="sxs-lookup"><span data-stu-id="f3780-114">Loop through the fields in the file.</span></span> <span data-ttu-id="f3780-115">Se sono presenti righe danneggiate, segnalare un errore e continuare l'analisi.</span><span class="sxs-lookup"><span data-stu-id="f3780-115">If any lines are corrupted, report an error and continue parsing.</span></span>  
  
     <span data-ttu-id="f3780-116">[!code-vb[VbFileIORead#11](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3780-116">[!code-vb[VbFileIORead#11](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_3.vb)]</span></span>  
  
4.  <span data-ttu-id="f3780-117">Chiudere i blocchi `While` e `Using` con `End While` ed `End Using`.</span><span class="sxs-lookup"><span data-stu-id="f3780-117">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     <span data-ttu-id="f3780-118">[!code-vb[VbFileIORead#12](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3780-118">[!code-vb[VbFileIORead#12](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3780-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="f3780-119">Example</span></span>  
 <span data-ttu-id="f3780-120">Nell'esempio riportato di seguito viene letto il file `test.log`.</span><span class="sxs-lookup"><span data-stu-id="f3780-120">This example reads from the file `test.log`.</span></span>  
  
 <span data-ttu-id="f3780-121">[!code-vb[VbFileIORead#13](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3780-121">[!code-vb[VbFileIORead#13](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_5.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f3780-122">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="f3780-122">Robust programming</span></span>  
 <span data-ttu-id="f3780-123">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="f3780-123">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="f3780-124">Impossibile analizzare la riga usando il formato specificato (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="f3780-124">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="f3780-125">Il messaggio di eccezione specifica la riga che ha generato l'eccezione, mentre alla proprietà <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> viene assegnato il testo contenuto nella riga.</span><span class="sxs-lookup"><span data-stu-id="f3780-125">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned to the text contained in the line.</span></span>  
  
-   <span data-ttu-id="f3780-126">File specificato inesistente (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="f3780-126">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="f3780-127">Un contesto di attendibilità parziale in cui gli utenti non dispongono di autorizzazioni sufficienti per accedere al file</span><span class="sxs-lookup"><span data-stu-id="f3780-127">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="f3780-128">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="f3780-128">(<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="f3780-129">Percorso del file troppo lungo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="f3780-129">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="f3780-130">L'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="f3780-130">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3780-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3780-131">See also</span></span>  
 <span data-ttu-id="f3780-132"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f3780-132"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span></span>   
 <span data-ttu-id="f3780-133">[Procedura: Leggere da file di testo con valori delimitati da virgole](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="f3780-133">[How to: Read From Comma-Delimited Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md) </span></span>  
 <span data-ttu-id="f3780-134">[Procedura: Leggere da file di testo con più formati](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span><span class="sxs-lookup"><span data-stu-id="f3780-134">[How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span></span>  
 <span data-ttu-id="f3780-135">[Analisi dei file di testo con l'oggetto TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md) </span><span class="sxs-lookup"><span data-stu-id="f3780-135">[Parsing Text Files with the TextFieldParser Object](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md) </span></span>  
 <span data-ttu-id="f3780-136">[Procedura dettagliata: Modifica di file e directory in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md) </span><span class="sxs-lookup"><span data-stu-id="f3780-136">[Walkthrough: Manipulating Files and Directories in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md) </span></span>  
 [<span data-ttu-id="f3780-137">Risoluzione dei problemi: lettura e scrittura nei file di testo</span><span class="sxs-lookup"><span data-stu-id="f3780-137">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 

