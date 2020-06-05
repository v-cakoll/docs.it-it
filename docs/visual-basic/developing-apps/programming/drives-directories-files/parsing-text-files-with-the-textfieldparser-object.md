---
title: Analisi dei file di testo con l'oggetto TextFieldParser
ms.date: 07/20/2015
helpviewer_keywords:
- TextFieldParser object, using
- I/O [Visual Basic], parsing files
- files [Visual Basic], parsing
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
ms.openlocfilehash: 7b2cb0dd39d14dd94db661cc9cbacf99edf0e778
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406677"
---
# <a name="parsing-text-files-with-the-textfieldparser-object-visual-basic"></a><span data-ttu-id="92cbd-102">Analisi dei file di testo con l'oggetto TextFieldParser (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92cbd-102">Parsing text files with the TextFieldParser object (Visual Basic)</span></span>

<span data-ttu-id="92cbd-103">L'oggetto `TextFieldParser` consente di analizzare ed elaborare file di grandi dimensioni strutturati come colonne di testo a larghezza delimitata, ad esempio i file di log e le informazioni sul database legacy.</span><span class="sxs-lookup"><span data-stu-id="92cbd-103">The `TextFieldParser` object allows you to parse and process very large file that are structured as delimited-width columns of text, such as log files or legacy database information.</span></span> <span data-ttu-id="92cbd-104">L'analisi di un file di testo con `TextFieldParser` è simile all'esecuzione di un'iterazione di un file di testo, mentre l'uso del metodo di analisi per l'estrazione dei campi di testo è analogo ai metodi di modifica delle stringhe usati per rappresentare in formato tokene le stringhe delimitate.</span><span class="sxs-lookup"><span data-stu-id="92cbd-104">Parsing a text file with `TextFieldParser` is similar to iterating over a text file, while the parse method to extract fields of text is similar to string manipulation methods used to tokenize delimited strings.</span></span>  
  
## <a name="parsing-different-types-of-text-files"></a><span data-ttu-id="92cbd-105">Analisi dei diversi tipi di file di testo</span><span class="sxs-lookup"><span data-stu-id="92cbd-105">Parsing different types of text files</span></span>  

 <span data-ttu-id="92cbd-106">I file di testo possono contenere campi di larghezza diversa delimitati da caratteri, ad esempio da una virgola o da uno spazio di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="92cbd-106">Text files may have fields of various width, delimited by a character such as a comma or a tab space.</span></span> <span data-ttu-id="92cbd-107">Definire `TextFieldType` e il delimitatore, come illustrato nell'esempio seguente, dove viene usato il metodo `SetDelimiters` per definire un file di testo delimitato da tabulazioni:</span><span class="sxs-lookup"><span data-stu-id="92cbd-107">Define `TextFieldType` and the delimiter, as in the following example, which uses the `SetDelimiters` method to define a tab-delimited text file:</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#21)]  
  
 <span data-ttu-id="92cbd-108">Altri file di testo potrebbero contenere larghezze di campo fisse.</span><span class="sxs-lookup"><span data-stu-id="92cbd-108">Other text files may have field widths that are fixed.</span></span> <span data-ttu-id="92cbd-109">In questi casi è necessario definire `TextFieldType` come `FixedWidth` e stabilire la larghezza di ogni campo, come nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="92cbd-109">In such cases, you need to define the `TextFieldType` as `FixedWidth` and define the widths of each field, as in the following example.</span></span> <span data-ttu-id="92cbd-110">In questo esempio viene usato il metodo `SetFieldWidths` per definire le colonne di testo: la prima colonna ha una larghezza di 5 caratteri, la seconda di 10, la terza di 11 e la quarta è di larghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="92cbd-110">This example uses the `SetFieldWidths` method to define the columns of text: the first column is 5 characters wide, the second is 10, the third is 11, and the fourth is of variable width.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#22)]  
  
 <span data-ttu-id="92cbd-111">Dopo aver definito il formato, è possibile riprodurre a ciclo continuo il file usando il metodo `ReadFields` per elaborare una riga per volta.</span><span class="sxs-lookup"><span data-stu-id="92cbd-111">Once the format is defined, you can loop through the file, using the `ReadFields` method to process each line in turn.</span></span>  
  
 <span data-ttu-id="92cbd-112">Se un campo non corrisponde al formato specificato viene generata l'eccezione <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>.</span><span class="sxs-lookup"><span data-stu-id="92cbd-112">If a field does not match the specified format, a <xref:Microsoft.VisualBasic.FileIO.MalformedLineException> exception is thrown.</span></span> <span data-ttu-id="92cbd-113">Quando vengono generate eccezioni di questo genere, le proprietà `ErrorLine` e `ErrorLineNumber` contengono il testo che genera l'eccezione e il numero di riga corrispondente.</span><span class="sxs-lookup"><span data-stu-id="92cbd-113">When such exceptions are thrown, the `ErrorLine` and `ErrorLineNumber` properties hold the text causing the exception and the line number of that text.</span></span>  
  
## <a name="parsing-files-with-multiple-formats"></a><span data-ttu-id="92cbd-114">Analisi dei file con più formati</span><span class="sxs-lookup"><span data-stu-id="92cbd-114">Parsing files with multiple formats</span></span>  

 <span data-ttu-id="92cbd-115">Il metodo `PeekChars` dell'oggetto `TextFieldParser` può essere usato per controllare ogni campo prima che venga letto, consentendo così di definire più formati per i campi e reagire di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="92cbd-115">The `PeekChars` method of the `TextFieldParser` object can be used to check each field before reading it, allowing you to define multiple formats for the fields and react accordingly.</span></span> <span data-ttu-id="92cbd-116">Per altre informazioni, vedere [Procedura: Leggere da file di testo con più formati](how-to-read-from-text-files-with-multiple-formats.md).</span><span class="sxs-lookup"><span data-stu-id="92cbd-116">For more information, see [How to: Read From Text Files with Multiple Formats](how-to-read-from-text-files-with-multiple-formats.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92cbd-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92cbd-117">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ReadFields%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLineNumber%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.HasFieldsEnclosedInQuotes%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.LineNumber%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TrimWhiteSpace%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A>
