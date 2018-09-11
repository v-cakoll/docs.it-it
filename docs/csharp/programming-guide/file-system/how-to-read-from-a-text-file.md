---
title: 'Procedura: leggere da un file di testo (Guida per programmatori C#)'
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: cb7f5c0239273c04f9f89b4e63335e67fdf5419a
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44084117"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a>Procedura: leggere da un file di testo (Guida per programmatori C#)
Questo esempio legge il contenuto di un file di testo usando i metodi statici <xref:System.IO.File.ReadAllText%2A> e <xref:System.IO.File.ReadAllLines%2A> della classe <xref:System.IO.File?displayProperty=nameWithType>.  
  
 Per un esempio che usa <xref:System.IO.StreamReader>, vedere [Procedura: leggere un file di testo una riga alla volta](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).  
  
> [!NOTE]
>  I file che vengono usati in questo esempio sono creati nell'argomento [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md) (Procedura: scrivere un file di testo).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Copiare il codice e incollarlo in un'applicazione console C#.  
  
 Se non si usano i file di testo da [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md) (Procedura: scrivere un file di testo), sostituire l'argomento `ReadAllText` e `ReadAllLines` con il nome file e il percorso appropriati nel computer in uso.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   Il file non esiste o non esiste nella posizione specificata. Controllare il percorso e la digitazione del nome file.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Non basarsi sul nome di un file per determinare il contenuto del file. Ad esempio, il file `myFile.cs` potrebbe non essere un file di origine C#.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO?displayProperty=nameWithType>  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [File system e Registro di sistema (Guida per programmatori C#)](../../../csharp/programming-guide/file-system/index.md)
