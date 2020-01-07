---
title: Come leggere da un file di testo- C# Guida alla programmazione
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: 4e15d82a303c1a92739c72a2ddffd411debf99d4
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635327"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a>Come leggere da un file di testo (C# guida per programmatori)
Questo esempio legge il contenuto di un file di testo usando i metodi statici <xref:System.IO.File.ReadAllText%2A> e <xref:System.IO.File.ReadAllLines%2A> della classe <xref:System.IO.File?displayProperty=nameWithType>.  
  
Per un esempio che usa <xref:System.IO.StreamReader>, vedere [come leggere un file di testo una riga alla volta](./how-to-read-a-text-file-one-line-at-a-time.md).
  
> [!NOTE]
> I file usati in questo esempio vengono creati nell'argomento [come scrivere in un file di testo](./how-to-write-to-a-text-file.md).
  
## <a name="example"></a>Esempio  
 [!code-csharp[csFilesandFolders#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#4)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Copiare il codice e incollarlo in un'applicazione console C#.  
  
Se non si utilizzano i file di testo da [come scrivere in un file di testo](./how-to-write-to-a-text-file.md), sostituire l'argomento con `ReadAllText` e `ReadAllLines` con il percorso e il nome file appropriati nel computer.
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
- Il file non esiste o non esiste nella posizione specificata. Controllare il percorso e la digitazione del nome file.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Non basarsi sul nome di un file per determinare il contenuto del file. Ad esempio, il file `myFile.cs` potrebbe non essere un file di origine C#.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO?displayProperty=nameWithType>
- [Guida per programmatori C#](../index.md)
- [File system e Registro di sistema (Guida per programmatori C#)](./index.md)
