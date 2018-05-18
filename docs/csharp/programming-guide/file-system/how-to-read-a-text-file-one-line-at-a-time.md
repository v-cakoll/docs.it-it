---
title: 'Procedura: leggere un file di testo una riga alla volta (Visual C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
ms.openlocfilehash: 2ed0069f9313955edc2cc46ecfd395a5f1ac2852
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-a-text-file-one-line-at-a-time-visual-c"></a>Procedura: leggere un file di testo una riga alla volta (Visual C#)
Questo esempio legge il contenuto di un file di testo, una riga alla volta, in una stringa usando il metodo `ReadLine` della classe `StreamReader`. Ogni riga di testo è memorizzata nella stringa `line` e visualizzata nella schermata.  
  
## <a name="example"></a>Esempio  
  
```  
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =   
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine (line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Copiare il codice e incollarlo nel metodo `Main` di un'applicazione console.  
  
 Sostituire `"c:\test.txt"` con il nome effettivo del file.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   È possibile che il file non esista.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto. Ad esempio, il file `myFile.cs` potrebbe non essere un file di origine C#.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO?displayProperty=nameWithType>  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [File system e Registro di sistema (Guida per programmatori C#)](../../../csharp/programming-guide/file-system/index.md)
