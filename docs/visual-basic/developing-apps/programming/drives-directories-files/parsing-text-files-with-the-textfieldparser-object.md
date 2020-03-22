---
title: Analisi dei file di testo con l'oggetto TextFieldParser
ms.date: 07/20/2015
helpviewer_keywords:
- TextFieldParser object, using
- I/O [Visual Basic], parsing files
- files [Visual Basic], parsing
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
ms.openlocfilehash: f3239184beb58312a8e3598545fc37423ff85287
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74333851"
---
# <a name="parsing-text-files-with-the-textfieldparser-object-visual-basic"></a>Analisi dei file di testo con l'oggetto TextFieldParser (Visual Basic)

L'oggetto `TextFieldParser` consente di analizzare ed elaborare file di grandi dimensioni strutturati come colonne di testo a larghezza delimitata, ad esempio i file di log e le informazioni sul database legacy. L'analisi di un file di testo con `TextFieldParser` è simile all'esecuzione di un'iterazione di un file di testo, mentre l'uso del metodo di analisi per l'estrazione dei campi di testo è analogo ai metodi di modifica delle stringhe usati per rappresentare in formato tokene le stringhe delimitate.  
  
## <a name="parsing-different-types-of-text-files"></a>Analisi dei diversi tipi di file di testo  

 I file di testo possono contenere campi di larghezza diversa delimitati da caratteri, ad esempio da una virgola o da uno spazio di tabulazione. Definire `TextFieldType` e il delimitatore, come illustrato nell'esempio seguente, dove viene usato il metodo `SetDelimiters` per definire un file di testo delimitato da tabulazioni:  
  
 [!code-vb[VbVbalrTextFieldParser#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#21)]  
  
 Altri file di testo potrebbero contenere larghezze di campo fisse. In questi casi è necessario definire `TextFieldType` come `FixedWidth` e stabilire la larghezza di ogni campo, come nell'esempio riportato di seguito. In questo esempio viene usato il metodo `SetFieldWidths` per definire le colonne di testo: la prima colonna ha una larghezza di 5 caratteri, la seconda di 10, la terza di 11 e la quarta è di larghezza variabile.  
  
 [!code-vb[VbVbalrTextFieldParser#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#22)]  
  
 Dopo aver definito il formato, è possibile riprodurre a ciclo continuo il file usando il metodo `ReadFields` per elaborare una riga per volta.  
  
 Se un campo non corrisponde al formato specificato viene generata l'eccezione <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>. Quando vengono generate eccezioni di questo genere, le proprietà `ErrorLine` e `ErrorLineNumber` contengono il testo che genera l'eccezione e il numero di riga corrispondente.  
  
## <a name="parsing-files-with-multiple-formats"></a>Analisi dei file con più formati  

 Il metodo `PeekChars` dell'oggetto `TextFieldParser` può essere usato per controllare ogni campo prima che venga letto, consentendo così di definire più formati per i campi e reagire di conseguenza. Per altre informazioni, vedere [Procedura: Leggere da file di testo con più formati](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).  
  
## <a name="see-also"></a>Vedere anche

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
