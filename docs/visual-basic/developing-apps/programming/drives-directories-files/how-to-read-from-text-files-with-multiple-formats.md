---
title: 'Procedura: Leggere da file di testo con più formati in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- TextFieldParser object, reading from a file
- TextFieldType enumeration
- My.Computer.FileSystem.WriteAllText method, parsing structured text files
- WriteAllText method [Visual Basic], parsing structured text files
- PeekChars method [Visual Basic], determining format of text
- reading text files [Visual Basic], multiple formats
- I/O [Visual Basic], reading text files
- text files [Visual Basic], reading
ms.assetid: 8d185eb2-79ca-42cd-95a7-d3ff44a5a0f8
ms.openlocfilehash: eae60b2fc72ee8b8653d3a0517eeaaf8012e0372
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696747"
---
# <a name="how-to-read-from-text-files-with-multiple-formats-in-visual-basic"></a><span data-ttu-id="41e57-102">Procedura: Leggere da file di testo con più formati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41e57-102">How to: Read From Text Files with Multiple Formats in Visual Basic</span></span>
<span data-ttu-id="41e57-103">L'oggetto <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> consente di analizzare in modo facile ed efficace i file di testo strutturati, ad esempio i log.</span><span class="sxs-lookup"><span data-stu-id="41e57-103">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="41e57-104">È possibile elaborare un file con più formati usando il metodo `PeekChars` per determinare il formato di ogni riga durante l'analisi del file.</span><span class="sxs-lookup"><span data-stu-id="41e57-104">You can process a file with multiple formats by using the `PeekChars` method to determine the format of each line as you parse through the file.</span></span>  
  
### <a name="to-parse-a-text-file-with-multiple-formats"></a><span data-ttu-id="41e57-105">Per analizzare un file di testo con più formati</span><span class="sxs-lookup"><span data-stu-id="41e57-105">To parse a text file with multiple formats</span></span>  
  
1. <span data-ttu-id="41e57-106">Aggiungere un file di testo denominato testfile.txt al progetto.</span><span class="sxs-lookup"><span data-stu-id="41e57-106">Add a text file named testfile.txt to your project.</span></span> <span data-ttu-id="41e57-107">Aggiungere quanto segue al file di testo.</span><span class="sxs-lookup"><span data-stu-id="41e57-107">Add the following content to the text file.</span></span>  
  
    ```text  
    Err  1001 Cannot access resource.  
    Err  2014 Resource not found.  
    Acc  10/03/2009User1      Administrator.  
    Err  0323 Warning: Invalid access attempt.  
    Acc  10/03/2009User2      Standard user.  
    Acc  10/04/2009User2      Standard user.  
    ```  
  
2. <span data-ttu-id="41e57-108">Definire il formato previsto e il formato usato al momento della segnalazione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="41e57-108">Define the expected format and the format used when an error is reported.</span></span> <span data-ttu-id="41e57-109">L'ultima voce in ogni matrice è -1, pertanto si presuppone che l'ultimo campo sia di larghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="41e57-109">The last entry in each array is -1, therefore the last field is assumed to be of variable width.</span></span> <span data-ttu-id="41e57-110">Tale occorrenza si verifica quando l'ultima voce nella matrice è minore o uguale a 0.</span><span class="sxs-lookup"><span data-stu-id="41e57-110">This occurs when the last entry in the array is less than or equal to 0.</span></span>  
  
     [!code-vb[VbFileIORead#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#4)]  
  
3. <span data-ttu-id="41e57-111">Creare un nuovo oggetto <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>, specificando la larghezza e il formato.</span><span class="sxs-lookup"><span data-stu-id="41e57-111">Create a new <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object, defining the width and format.</span></span>  
  
     [!code-vb[VbFileIORead#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#5)]  
  
4. <span data-ttu-id="41e57-112">Scorrere le righe, verificando il formato prima della lettura.</span><span class="sxs-lookup"><span data-stu-id="41e57-112">Loop through the rows, testing for format before reading.</span></span>  
  
     [!code-vb[VbFileIORead#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#6)]  
  
5. <span data-ttu-id="41e57-113">Scrivere gli errori nella console.</span><span class="sxs-lookup"><span data-stu-id="41e57-113">Write errors to the console.</span></span>  
  
     [!code-vb[VbFileIORead#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#7)]  
  
## <a name="example"></a><span data-ttu-id="41e57-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="41e57-114">Example</span></span>  
 <span data-ttu-id="41e57-115">Di seguito è riportato l'esempio completo di lettura dal file `testfile.txt`.</span><span class="sxs-lookup"><span data-stu-id="41e57-115">Following is the complete example that reads from the file `testfile.txt`.</span></span>  
  
 [!code-vb[VbFileIORead#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="41e57-116">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="41e57-116">Robust Programming</span></span>  
 <span data-ttu-id="41e57-117">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="41e57-117">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="41e57-118">Impossibile analizzare la riga usando il formato specificato (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="41e57-118">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="41e57-119">Il messaggio di eccezione specifica la riga che ha generato l'eccezione, mentre alla proprietà <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> viene assegnato il testo contenuto nella riga.</span><span class="sxs-lookup"><span data-stu-id="41e57-119">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned to the text contained in the line.</span></span>  
  
- <span data-ttu-id="41e57-120">File specificato inesistente (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="41e57-120">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="41e57-121">Un contesto di attendibilità parziale in cui gli utenti non dispongono di autorizzazioni sufficienti per accedere al file</span><span class="sxs-lookup"><span data-stu-id="41e57-121">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="41e57-122">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="41e57-122">(<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="41e57-123">Percorso del file troppo lungo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="41e57-123">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="41e57-124">L'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="41e57-124">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e57-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41e57-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>
- <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>
- [<span data-ttu-id="41e57-126">Procedura: Leggere da file di testo con valori delimitati da virgole</span><span class="sxs-lookup"><span data-stu-id="41e57-126">How to: Read From Comma-Delimited Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="41e57-127">Procedura: Leggere da file di testo a larghezza fissa</span><span class="sxs-lookup"><span data-stu-id="41e57-127">How to: Read From Fixed-width Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="41e57-128">Analisi dei file di testo con l'oggetto TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="41e57-128">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
