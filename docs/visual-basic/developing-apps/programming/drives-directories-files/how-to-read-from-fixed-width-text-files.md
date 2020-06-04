---
title: 'Procedura: leggere da file di testo a larghezza fissa'
ms.date: 07/20/2015
helpviewer_keywords:
- fixed-width text file
- reading text files [Visual Basic], fixed-width
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- text files [Visual Basic], reading
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
ms.openlocfilehash: 77b2e0a4ebe36b68501f821ef5731935ee3b16a7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411629"
---
# <a name="how-to-read-from-fixed-width-text-files-in-visual-basic"></a><span data-ttu-id="baa8e-102">Procedura: Leggere da file di testo a larghezza fissa in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="baa8e-102">How to: read from fixed-width text files in Visual Basic</span></span>

<span data-ttu-id="baa8e-103">L'oggetto `TextFieldParser` consente di analizzare in modo facile ed efficace i file di testo strutturati, ad esempio i log.</span><span class="sxs-lookup"><span data-stu-id="baa8e-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span>  
  
 <span data-ttu-id="baa8e-104">La proprietà `TextFieldType` definisce se il file analizzato è un file delimitato o un file con campi di testo a larghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="baa8e-104">The `TextFieldType` property defines whether the parsed file is a delimited file or one that has fixed-width fields of text.</span></span> <span data-ttu-id="baa8e-105">In un file di testo a larghezza fissa il campo alla fine può avere una larghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="baa8e-105">In a fixed-width text file, the field at the end can have a variable width.</span></span> <span data-ttu-id="baa8e-106">Per specificare che il campo alla fine deve avere una larghezza variabile, definirlo in modo che abbia una larghezza minore o uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="baa8e-106">To specify that the field at the end has a variable width, define it to have a width less than or equal to zero.</span></span>  
  
### <a name="to-parse-a-fixed-width-text-file"></a><span data-ttu-id="baa8e-107">Per analizzare un file di testo a larghezza fissa</span><span class="sxs-lookup"><span data-stu-id="baa8e-107">To parse a fixed-width text file</span></span>  
  
1. <span data-ttu-id="baa8e-108">Creare un nuovo `TextFieldParser`.</span><span class="sxs-lookup"><span data-stu-id="baa8e-108">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="baa8e-109">Il codice riportato di seguito crea l'oggetto `TextFieldParser` denominato `Reader` e apre il file `test.log`.</span><span class="sxs-lookup"><span data-stu-id="baa8e-109">The following code creates the `TextFieldParser` named `Reader` and opens the file `test.log`.</span></span>  
  
     [!code-vb[VbFileIORead#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#9)]  
  
2. <span data-ttu-id="baa8e-110">Definire la proprietà `TextFieldType` come `FixedWidth`, impostandone la larghezza e il formato.</span><span class="sxs-lookup"><span data-stu-id="baa8e-110">Define the `TextFieldType` property as `FixedWidth`, defining the width and format.</span></span> <span data-ttu-id="baa8e-111">Il codice seguente definisce le colonne di testo: la prima ha una larghezza di 5 caratteri, la seconda di 10 e la terza di 11, mentre la quarta ha una larghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="baa8e-111">The following code defines the columns of text; the first is 5 characters wide, the second 10, the third 11, and the fourth is of variable width.</span></span>  
  
     [!code-vb[VbFileIORead#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#10)]  
  
3. <span data-ttu-id="baa8e-112">Eseguire il ciclo attraverso i campi nel file.</span><span class="sxs-lookup"><span data-stu-id="baa8e-112">Loop through the fields in the file.</span></span> <span data-ttu-id="baa8e-113">Se sono presenti righe danneggiate, segnalare un errore e continuare l'analisi.</span><span class="sxs-lookup"><span data-stu-id="baa8e-113">If any lines are corrupted, report an error and continue parsing.</span></span>  
  
     [!code-vb[VbFileIORead#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#11)]  
  
4. <span data-ttu-id="baa8e-114">Chiudere i blocchi `While` e `Using` con `End While` ed `End Using`.</span><span class="sxs-lookup"><span data-stu-id="baa8e-114">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     [!code-vb[VbFileIORead#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="baa8e-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="baa8e-115">Example</span></span>  

 <span data-ttu-id="baa8e-116">Nell'esempio riportato di seguito viene letto il file `test.log`.</span><span class="sxs-lookup"><span data-stu-id="baa8e-116">This example reads from the file `test.log`.</span></span>  
  
 [!code-vb[VbFileIORead#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#13)]  
  
## <a name="robust-programming"></a><span data-ttu-id="baa8e-117">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="baa8e-117">Robust programming</span></span>  

 <span data-ttu-id="baa8e-118">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="baa8e-118">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="baa8e-119">Impossibile analizzare la riga usando il formato specificato (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="baa8e-119">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="baa8e-120">Il messaggio di eccezione specifica la riga che ha generato l'eccezione, mentre alla proprietà <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> viene assegnato il testo contenuto nella riga.</span><span class="sxs-lookup"><span data-stu-id="baa8e-120">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned to the text contained in the line.</span></span>  
  
- <span data-ttu-id="baa8e-121">File specificato inesistente (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="baa8e-121">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="baa8e-122">Un contesto di attendibilità parziale in cui gli utenti non dispongono di autorizzazioni sufficienti per accedere al file</span><span class="sxs-lookup"><span data-stu-id="baa8e-122">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="baa8e-123">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="baa8e-123">(<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="baa8e-124">Percorso del file troppo lungo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="baa8e-124">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="baa8e-125">L'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="baa8e-125">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baa8e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baa8e-126">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [<span data-ttu-id="baa8e-127">Procedura: Leggere da file di testo con valori delimitati da virgole</span><span class="sxs-lookup"><span data-stu-id="baa8e-127">How to: Read From Comma-Delimited Text Files</span></span>](how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="baa8e-128">Procedura: Leggere da file di testo con più formati</span><span class="sxs-lookup"><span data-stu-id="baa8e-128">How to: Read From Text Files with Multiple Formats</span></span>](how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="baa8e-129">Analisi dei file di testo con l'oggetto TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="baa8e-129">Parsing Text Files with the TextFieldParser Object</span></span>](parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="baa8e-130">Procedura dettagliata: Modifica di file e directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="baa8e-130">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](walkthrough-manipulating-files-and-directories.md)
- [<span data-ttu-id="baa8e-131">Risoluzione dei problemi: Lettura e scrittura nei file di testo</span><span class="sxs-lookup"><span data-stu-id="baa8e-131">Troubleshooting: Reading from and Writing to Text Files</span></span>](troubleshooting-reading-from-and-writing-to-text-files.md)
