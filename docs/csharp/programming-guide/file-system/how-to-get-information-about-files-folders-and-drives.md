---
title: Come ottenere informazioni su file, cartelle e unità- C# Guida alla programmazione
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
ms.openlocfilehash: e8bd65b1c8c24f69d280cf69deaf25daf7cf8818
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635392"
---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a>Come ottenere informazioni su file, cartelle e unità (C# guida per programmatori)
In .NET Framework è possibile accedere a informazioni sul file system mediante le classi seguenti:  
  
- <xref:System.IO.FileInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DirectoryInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DriveInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.Directory?displayProperty=nameWithType>  
  
- <xref:System.IO.File?displayProperty=nameWithType>  
  
 Le classi <xref:System.IO.FileInfo> e <xref:System.IO.DirectoryInfo> rappresentano un file o una directory e contengono proprietà che espongono molti degli attributi di file supportati dal file system NTFS. Contengono anche i metodi per l'apertura, la chiusura, lo spostamento e l'eliminazione di file e cartelle. È possibile creare istanze di queste classi passando al costruttore una stringa che rappresenta il nome del file, della cartella o dell'unità:  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 È anche possibile ottenere i nomi di file, cartelle o unità tramite chiamate a <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType> e <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType>.  
  
 Le classi <xref:System.IO.Directory?displayProperty=nameWithType> e <xref:System.IO.File?displayProperty=nameWithType> forniscono metodi statici per il recupero di informazioni su file e directory.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra vari modi per accedere alle informazioni su file e cartelle.  
  
 [!code-csharp[csFilesandFolders#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#6)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Quando si elaborano stringhe di percorso specificate dall'utente, occorre gestire anche le eccezioni per le condizioni seguenti:  
  
- Il nome file non è valido. Ad esempio, contiene caratteri non validi o solo spazi vuoti.  
  
- Il nome del file è Null.  
  
- La lunghezza del nome del file è maggiore della lunghezza massima definita nel sistema.  
  
- Il nome del file contiene i due punti (:).  
  
 Se l'applicazione non ha autorizzazioni sufficienti per leggere il file specificato, il metodo `Exists` restituisce `false` indipendentemente dal fatto che il percorso esista. Il metodo non genera un'eccezione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO?displayProperty=nameWithType>
- [Guida per programmatori C#](../index.md)
- [File system e Registro di sistema (Guida per programmatori C#)](./index.md)
