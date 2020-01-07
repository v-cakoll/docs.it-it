---
title: Come creare un file o una cartella- C# Guida alla programmazione
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
ms.openlocfilehash: 97231a2e4818be3b99c796a407ae4b167e27f669
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635704"
---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a>Come creare un file o una cartella (C# guida per programmatori)
A livello di codice è possibile creare una cartella, una sottocartella e un file nella sottocartella e quindi scrivere dati nel file.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csFilesandFolders#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#10)]  
  
 Se la cartella esiste già, <xref:System.IO.Directory.CreateDirectory%2A> non esegue alcuna operazione e non viene generata alcuna eccezione. <xref:System.IO.File.Create%2A?displayProperty=nameWithType>, tuttavia, sostituisce un file esistente con un nuovo file. Nell'esempio viene usata un'istruzione `if`-`else` per evitare la sostituzione di un file esistente.  
  
 Apportando le modifiche seguenti nell'esempio, è possibile specificare risultati diversi in base all'esistenza o meno di un file con un determinato nome. Se il file non esiste, il codice ne crea uno. Se il file esiste, il codice aggiunge i dati a questo.  
  
- Specificare un nome file non casuale.  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
- Sostituire l'istruzione `if`-`else` con l'istruzione `using` riportata nel codice seguente.  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
    ```  
  
 Eseguire l'esempio più volte per verificare che i dati vengano aggiunti al file ogni volta.  
  
 Per altri valori `FileMode` da provare, vedere <xref:System.IO.FileMode>.  
  
 Le seguenti condizioni possono generare un'eccezione:  
  
- Il formato del nome della cartella non è valido. Ad esempio, contiene caratteri non validi o è costituito solo da spazi (classe <xref:System.ArgumentException>). Per creare nomi di percorso validi, usare la classe <xref:System.IO.Path>.  
  
- La cartella padre della cartella da creare è di sola lettura (classe <xref:System.IO.IOException>).  
  
- Il nome della cartella è `null` (classe <xref:System.ArgumentNullException>).  
  
- Il nome della cartella è troppo lungo (classe <xref:System.IO.PathTooLongException>).  
  
- Il nome della cartella è composto solo da un carattere due punti, ":" (classe <xref:System.IO.PathTooLongException>).  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 In situazioni di attendibilità parziale può essere generata un'istanza della classe <xref:System.Security.SecurityException>.  
  
 Se l'utente non è autorizzato a creare la cartella, l'esempio genera un'istanza della classe <xref:System.UnauthorizedAccessException>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO?displayProperty=nameWithType>
- [Guida per programmatori C#](../index.md)
- [File system e Registro di sistema (Guida per programmatori C#)](./index.md)
