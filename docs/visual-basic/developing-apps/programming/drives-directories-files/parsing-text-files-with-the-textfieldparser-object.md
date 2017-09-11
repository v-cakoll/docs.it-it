---
title: Analisi dei file di testo con l'oggetto TextFieldParser (Visual Basic)
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
- TextFieldParser object, using
- I/O [Visual Basic], parsing files
- files, parsing
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
caps.latest.revision: 20
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
ms.openlocfilehash: ad7407ca1928f9b4a2405bc5831777fbf965b61f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="parsing-text-files-with-the-textfieldparser-object-visual-basic"></a><span data-ttu-id="a1ec0-102">Analisi dei file di testo con l'oggetto TextFieldParser (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1ec0-102">Parsing text files with the TextFieldParser object (Visual Basic)</span></span>
<span data-ttu-id="a1ec0-103">L'oggetto `TextFieldParser` consente di analizzare ed elaborare file di grandi dimensioni strutturati come colonne di testo a larghezza delimitata, ad esempio i file di log e le informazioni sul database legacy.</span><span class="sxs-lookup"><span data-stu-id="a1ec0-103">The `TextFieldParser` object allows you to parse and process very large file that are structured as delimited-width columns of text, such as log files or legacy database information.</span></span> <span data-ttu-id="a1ec0-104">L'analisi di un file di testo con `TextFieldParser` è simile all'esecuzione di un'iterazione di un file di testo, mentre l'uso del metodo di analisi per l'estrazione dei campi di testo è analogo ai metodi di modifica delle stringhe usati per rappresentare in formato tokene le stringhe delimitate.</span><span class="sxs-lookup"><span data-stu-id="a1ec0-104">Parsing a text file with `TextFieldParser` is similar to iterating over a text file, while the parse method to extract fields of text is similar to string manipulation methods used to tokenize delimited strings.</span></span>  
  
## <a name="parsing-different-types-of-text-files"></a><span data-ttu-id="a1ec0-105">Analisi dei diversi tipi di file di testo</span><span class="sxs-lookup"><span data-stu-id="a1ec0-105">Parsing different types of text files</span></span>  
 <span data-ttu-id="a1ec0-106">I file di testo possono contenere campi di larghezza diversa delimitati da caratteri, ad esempio da una virgola o da uno spazio di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="a1ec0-106">Text files may have fields of various width, delimited by a character such as a comma or a tab space.</span></span> <span data-ttu-id="a1ec0-107">Definire `TextFieldType` e il delimitatore, come illustrato nell'esempio seguente, dove viene usato il metodo `SetDelimiters` per definire un file di testo delimitato da tabulazioni:</span><span class="sxs-lookup"><span data-stu-id="a1ec0-107">Define `TextFieldType` and the delimiter, as in the following example, which uses the `SetDelimiters` method to define a tab-delimited text file:</span></span>  
  
 <span data-ttu-id="a1ec0-108">[!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a1ec0-108">[!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_1.vb)]</span></span>  
  
 <span data-ttu-id="a1ec0-109">Altri file di testo potrebbero contenere larghezze di campo fisse.</span><span class="sxs-lookup"><span data-stu-id="a1ec0-109">Other text files may have field widths that are fixed.</span></span> <span data-ttu-id="a1ec0-110">In questi casi è necessario definire `TextFieldType` come `FixedWidth` e stabilire la larghezza di ogni campo, come nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a1ec0-110">In such cases, you need to define the `TextFieldType` as `FixedWidth` and define the widths of each field, as in the following example.</span></span> <span data-ttu-id="a1ec0-111">In questo esempio viene usato il metodo `SetFieldWidths` per definire le colonne di testo: la prima colonna ha una larghezza di 5 caratteri, la seconda di 10, la terza di 11 e la quarta è di larghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="a1ec0-111">This example uses the `SetFieldWidths` method to define the columns of text: the first column is 5 characters wide, the second is 10, the third is 11, and the fourth is of variable width.</span></span>  
  
 <span data-ttu-id="a1ec0-112">[!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a1ec0-112">[!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_2.vb)]</span></span>  
  
 <span data-ttu-id="a1ec0-113">Dopo aver definito il formato, è possibile riprodurre a ciclo continuo il file usando il metodo `ReadFields` per elaborare una riga per volta.</span><span class="sxs-lookup"><span data-stu-id="a1ec0-113">Once the format is defined, you can loop through the file, using the `ReadFields` method to process each line in turn.</span></span>  
  
 <span data-ttu-id="a1ec0-114">Se un campo non corrisponde al formato specificato viene generata l'eccezione <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>.</span><span class="sxs-lookup"><span data-stu-id="a1ec0-114">If a field does not match the specified format, a <xref:Microsoft.VisualBasic.FileIO.MalformedLineException> exception is thrown.</span></span> <span data-ttu-id="a1ec0-115">Quando vengono generate eccezioni di questo genere, le proprietà `ErrorLine` e `ErrorLineNumber` contengono il testo che genera l'eccezione e il numero di riga corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a1ec0-115">When such exceptions are thrown, the `ErrorLine` and `ErrorLineNumber` properties hold the text causing the exception and the line number of that text.</span></span>  
  
## <a name="parsing-files-with-multiple-formats"></a><span data-ttu-id="a1ec0-116">Analisi dei file con più formati</span><span class="sxs-lookup"><span data-stu-id="a1ec0-116">Parsing files with multiple formats</span></span>  
 <span data-ttu-id="a1ec0-117">Il metodo `PeekChars` dell'oggetto `TextFieldParser` può essere usato per controllare ogni campo prima che venga letto, consentendo così di definire più formati per i campi e reagire di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="a1ec0-117">The `PeekChars` method of the `TextFieldParser` object can be used to check each field before reading it, allowing you to define multiple formats for the fields and react accordingly.</span></span> <span data-ttu-id="a1ec0-118">Per altre informazioni, vedere [Procedura: Leggere da file di testo con più formati](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).</span><span class="sxs-lookup"><span data-stu-id="a1ec0-118">For more information, see [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1ec0-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1ec0-119">See also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ReadFields%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.HasFieldsEnclosedInQuotes%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.LineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TrimWhiteSpace%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A>

