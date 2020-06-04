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
# <a name="how-to-read-from-comma-delimited-text-files-in-visual-basic"></a>Procedura: Leggere da file di testo con valori delimitati da virgole in Visual Basic

L'oggetto `TextFieldParser` consente di analizzare in modo facile ed efficace i file di testo strutturati, ad esempio i log. La proprietà `TextFieldType` definisce se si tratta di un file delimitato o di un file con campi di testo a larghezza fissa.  
  
### <a name="to-parse-a-comma-delimited-text-file"></a>Per analizzare un file di testo con valori delimitati da virgole  
  
1. Creare un nuovo `TextFieldParser`. Il codice riportato di seguito crea l'oggetto `TextFieldParser` denominato `MyReader` e apre il file `test.txt`.  
  
     [!code-vb[VbFileIORead#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#15)]  
  
2. Definire il tipo `TextField` e il delimitatore. Nel codice riportato di seguito viene definita la proprietà `TextFieldType` come `Delimited` e il delimitatore come ",".  
  
     [!code-vb[VbFileIORead#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#16)]  
  
3. Eseguire il ciclo attraverso i campi nel file. Se sono presenti righe danneggiate, segnalare un errore e continuare l'analisi. Nel codice riportato di seguito viene eseguito un ciclo attraverso il file, visualizzando ogni campo e segnalando eventuali campi formattati in modo errato.  
  
     [!code-vb[VbFileIORead#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#17)]  
  
4. Chiudere i blocchi `While` e `Using` con `End While` ed `End Using`.  
  
     [!code-vb[VbFileIORead#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#18)]  
  
## <a name="example"></a>Esempio  

 Nell'esempio riportato di seguito viene letto il file `test.txt`.  
  
 [!code-vb[VbFileIORead#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#19)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  

 Le seguenti condizioni possono generare un'eccezione:  
  
- Impossibile analizzare la riga usando il formato specificato (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>). Il messaggio di eccezione specifica la riga che ha generato l'eccezione, mentre alla proprietà <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> viene assegnato il testo contenuto nella riga.  
  
- File specificato inesistente (<xref:System.IO.FileNotFoundException>).  
  
- Un contesto di attendibilità parziale in cui gli utenti non dispongono di autorizzazioni sufficienti per accedere al file (<xref:System.Security.SecurityException>).  
  
- Percorso del file troppo lungo (<xref:System.IO.PathTooLongException>).  
  
- L'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [Procedura: Leggere da file di testo a larghezza fissa](how-to-read-from-fixed-width-text-files.md)
- [Procedura: Leggere da file di testo con più formati](how-to-read-from-text-files-with-multiple-formats.md)
- [Analisi dei file di testo con l'oggetto TextFieldParser](parsing-text-files-with-the-textfieldparser-object.md)
- [Procedura dettagliata: Modifica di file e directory in Visual Basic](walkthrough-manipulating-files-and-directories.md)
- [Risoluzione dei problemi: Lettura e scrittura nei file di testo](troubleshooting-reading-from-and-writing-to-text-files.md)
