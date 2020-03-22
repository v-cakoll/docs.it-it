---
title: 'Procedura: leggere da file di testo con più formatiHow to: Read from text files with multiple formats'
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
ms.openlocfilehash: b36c781d5f8333749d346bb8f19540f0d1bd1692
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334576"
---
# <a name="how-to-read-from-fext-files-with-multiple-formats-in-visual-basic"></a>Procedura: leggere da file fext con più formati in Visual BasicHow to: Read from fext files with multiple formats in Visual Basic

L'oggetto <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> consente di analizzare in modo facile ed efficace i file di testo strutturati, ad esempio i log. È possibile elaborare un file con più formati usando il metodo `PeekChars` per determinare il formato di ogni riga durante l'analisi del file.
  
### <a name="to-parse-a-text-file-with-multiple-formats"></a>Per analizzare un file di testo con più formati

1. Aggiungere un file di testo denominato *testfile.txt* al progetto. Aggiungere il seguente contenuto al file di testo:

    ```text
    Err  1001 Cannot access resource.
    Err  2014 Resource not found.
    Acc  10/03/2009User1      Administrator.
    Err  0323 Warning: Invalid access attempt.
    Acc  10/03/2009User2      Standard user.
    Acc  10/04/2009User2      Standard user.
    ```

2. Definire il formato previsto e il formato usato al momento della segnalazione dell'errore. L'ultima voce in ogni matrice è -1, pertanto si presuppone che l'ultimo campo sia di larghezza variabile. Tale occorrenza si verifica quando l'ultima voce nella matrice è minore o uguale a 0.

     [!code-vb[VbFileIORead#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#4)]

3. Creare un nuovo oggetto <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>, specificando la larghezza e il formato.

     [!code-vb[VbFileIORead#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#5)]

4. Scorrere le righe, verificando il formato prima della lettura.

     [!code-vb[VbFileIORead#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#6)]

5. Scrivere gli errori nella console.

     [!code-vb[VbFileIORead#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#7)]

## <a name="example"></a>Esempio

Di seguito è riportato l'esempio `testfile.txt`completo che legge dal file:

 [!code-vb[VbFileIORead#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#8)]

## <a name="robust-programming"></a>Programmazione efficiente

Le seguenti condizioni possono generare un'eccezione:  
  
- Impossibile analizzare la riga usando il formato specificato (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>). Il messaggio di eccezione specifica la riga che ha generato l'eccezione, mentre alla proprietà <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> viene assegnato il testo contenuto nella riga.
- File specificato inesistente (<xref:System.IO.FileNotFoundException>).
- Un contesto di attendibilità parziale in cui gli utenti non dispongono di autorizzazioni sufficienti per accedere al file (<xref:System.Security.SecurityException>).
- Percorso del file troppo lungo (<xref:System.IO.PathTooLongException>).
- L'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.UnauthorizedAccessException>).

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>
- <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>
- [Procedura: leggere file di testo delimitati da virgola](how-to-read-from-comma-delimited-text-files.md)
- [Procedura: leggere file di testo a larghezza fissa](how-to-read-from-fixed-width-text-files.md)
- [Analisi dei file di testo con l'oggetto TextFieldParser](parsing-text-files-with-the-textfieldparser-object.md)
