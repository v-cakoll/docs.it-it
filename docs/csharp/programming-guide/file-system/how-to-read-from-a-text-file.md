---
title: Come leggere da un file di testo - Guida per programmatori C
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: d401a1d1bb2c6fccb203c440f367bd14c80e70e3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705015"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a>Come leggere da un file di testo (Guida per programmatori C
Questo esempio legge il contenuto di un file di testo usando i metodi statici <xref:System.IO.File.ReadAllText%2A> e <xref:System.IO.File.ReadAllLines%2A> della classe <xref:System.IO.File?displayProperty=nameWithType>.  
  
Per un esempio <xref:System.IO.StreamReader>in cui viene utilizzato , vedere Come leggere un file di [testo una riga alla volta.](./how-to-read-a-text-file-one-line-at-a-time.md)
  
> [!NOTE]
> I file utilizzati in questo esempio vengono creati nell'argomento Come scrivere in un file di [testo.](./how-to-write-to-a-text-file.md)
  
## <a name="example"></a>Esempio  
 [!code-csharp[csFilesandFolders#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#4)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Copiare il codice e incollarlo in un'applicazione console C#.  
  
Se non si utilizzano i file di testo da Come `ReadAllText` scrivere `ReadAllLines` in un file di [testo](./how-to-write-to-a-text-file.md), sostituire l'argomento in e con il percorso e il nome del file appropriati nel computer.
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
- Il file non esiste o non esiste nella posizione specificata. Controllare il percorso e la digitazione del nome file.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Non basarsi sul nome di un file per determinare il contenuto del file. Ad esempio, il file `myFile.cs` potrebbe non essere un file di origine C#.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO?displayProperty=nameWithType>
- [Guida per programmatori C#](../index.md)
- [File system e Registro di sistema (Guida per programmatori C#)](./index.md)
