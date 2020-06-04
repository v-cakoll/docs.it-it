---
title: 'Procedura: leggere da file di testo delimitati da virgole'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- reading text files [Visual Basic], comma-delimited
- text files [Visual Basic], reading
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
ms.openlocfilehash: ba62a0226a1a83326cbc7ab393d135763a7c7cb2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411642"
---
# <a name="how-to-read-from-comma-delimited-text-files-in-visual-basic"></a><span data-ttu-id="45109-102">Procedura: Leggere da file di testo con valori delimitati da virgole in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45109-102">How to: read from comma-delimited text files in Visual Basic</span></span>

<span data-ttu-id="45109-103">L'oggetto `TextFieldParser` consente di analizzare in modo facile ed efficace i file di testo strutturati, ad esempio i log.</span><span class="sxs-lookup"><span data-stu-id="45109-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="45109-104">La proprietà `TextFieldType` definisce se si tratta di un file delimitato o di un file con campi di testo a larghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="45109-104">The `TextFieldType` property defines whether it is a delimited file or one with fixed-width fields of text.</span></span>  
  
### <a name="to-parse-a-comma-delimited-text-file"></a><span data-ttu-id="45109-105">Per analizzare un file di testo con valori delimitati da virgole</span><span class="sxs-lookup"><span data-stu-id="45109-105">To parse a comma delimited text file</span></span>  
  
1. <span data-ttu-id="45109-106">Creare un nuovo `TextFieldParser`.</span><span class="sxs-lookup"><span data-stu-id="45109-106">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="45109-107">Il codice riportato di seguito crea l'oggetto `TextFieldParser` denominato `MyReader` e apre il file `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="45109-107">The following code creates the `TextFieldParser` named `MyReader` and opens the file `test.txt`.</span></span>  
  
     [!code-vb[VbFileIORead#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#15)]  
  
2. <span data-ttu-id="45109-108">Definire il tipo `TextField` e il delimitatore.</span><span class="sxs-lookup"><span data-stu-id="45109-108">Define the `TextField` type and delimiter.</span></span> <span data-ttu-id="45109-109">Nel codice riportato di seguito viene definita la proprietà `TextFieldType` come `Delimited` e il delimitatore come ",".</span><span class="sxs-lookup"><span data-stu-id="45109-109">The following code defines the `TextFieldType` property as `Delimited` and the delimiter as ",".</span></span>  
  
     [!code-vb[VbFileIORead#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#16)]  
  
3. <span data-ttu-id="45109-110">Eseguire il ciclo attraverso i campi nel file.</span><span class="sxs-lookup"><span data-stu-id="45109-110">Loop through the fields in the file.</span></span> <span data-ttu-id="45109-111">Se sono presenti righe danneggiate, segnalare un errore e continuare l'analisi.</span><span class="sxs-lookup"><span data-stu-id="45109-111">If any lines are corrupt, report an error and continue parsing.</span></span> <span data-ttu-id="45109-112">Nel codice riportato di seguito viene eseguito un ciclo attraverso il file, visualizzando ogni campo e segnalando eventuali campi formattati in modo errato.</span><span class="sxs-lookup"><span data-stu-id="45109-112">The following code loops through the file, displaying each field in turn and reporting any fields that are formatted incorrectly.</span></span>  
  
     [!code-vb[VbFileIORead#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#17)]  
  
4. <span data-ttu-id="45109-113">Chiudere i blocchi `While` e `Using` con `End While` ed `End Using`.</span><span class="sxs-lookup"><span data-stu-id="45109-113">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     [!code-vb[VbFileIORead#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#18)]  
  
## <a name="example"></a><span data-ttu-id="45109-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="45109-114">Example</span></span>  

 <span data-ttu-id="45109-115">Nell'esempio riportato di seguito viene letto il file `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="45109-115">This example reads from the file `test.txt`.</span></span>  
  
 [!code-vb[VbFileIORead#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#19)]  
  
## <a name="robust-programming"></a><span data-ttu-id="45109-116">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="45109-116">Robust programming</span></span>  

 <span data-ttu-id="45109-117">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="45109-117">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="45109-118">Impossibile analizzare la riga usando il formato specificato (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="45109-118">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="45109-119">Il messaggio di eccezione specifica la riga che ha generato l'eccezione, mentre alla proprietà <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> viene assegnato il testo contenuto nella riga.</span><span class="sxs-lookup"><span data-stu-id="45109-119">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned the text contained in the line.</span></span>  
  
- <span data-ttu-id="45109-120">File specificato inesistente (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="45109-120">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="45109-121">Un contesto di attendibilità parziale in cui gli utenti non dispongono di autorizzazioni sufficienti per accedere al file</span><span class="sxs-lookup"><span data-stu-id="45109-121">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="45109-122">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="45109-122">(<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="45109-123">Percorso del file troppo lungo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="45109-123">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="45109-124">L'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="45109-124">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45109-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45109-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [<span data-ttu-id="45109-126">Procedura: Leggere da file di testo a larghezza fissa</span><span class="sxs-lookup"><span data-stu-id="45109-126">How to: Read From Fixed-width Text Files</span></span>](how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="45109-127">Procedura: Leggere da file di testo con più formati</span><span class="sxs-lookup"><span data-stu-id="45109-127">How to: Read From Text Files with Multiple Formats</span></span>](how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="45109-128">Analisi dei file di testo con l'oggetto TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="45109-128">Parsing Text Files with the TextFieldParser Object</span></span>](parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="45109-129">Procedura dettagliata: Modifica di file e directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45109-129">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](walkthrough-manipulating-files-and-directories.md)
- [<span data-ttu-id="45109-130">Risoluzione dei problemi: Lettura e scrittura nei file di testo</span><span class="sxs-lookup"><span data-stu-id="45109-130">Troubleshooting: Reading from and Writing to Text Files</span></span>](troubleshooting-reading-from-and-writing-to-text-files.md)
