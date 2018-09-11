---
title: 'Procedura: ottenere informazioni relative a file, cartelle e unità (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
ms.openlocfilehash: 8ebacff0f3a1704ec001e3570d0df136f54baf9d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44206458"
---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a>Procedura: ottenere informazioni relative a file, cartelle e unità (Guida per programmatori C#)
In .NET Framework è possibile accedere a informazioni sul file system mediante le classi seguenti:  
  
-   <xref:System.IO.FileInfo?displayProperty=nameWithType>  
  
-   <xref:System.IO.DirectoryInfo?displayProperty=nameWithType>  
  
-   <xref:System.IO.DriveInfo?displayProperty=nameWithType>  
  
-   <xref:System.IO.Directory?displayProperty=nameWithType>  
  
-   <xref:System.IO.File?displayProperty=nameWithType>  
  
 Le classi <xref:System.IO.FileInfo> e <xref:System.IO.DirectoryInfo> rappresentano un file o una directory e contengono proprietà che espongono molti degli attributi di file supportati dal file system NTFS. Contengono anche i metodi per l'apertura, la chiusura, lo spostamento e l'eliminazione di file e cartelle. È possibile creare istanze di queste classi passando al costruttore una stringa che rappresenta il nome del file, della cartella o dell'unità:  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 È anche possibile ottenere i nomi di file, cartelle o unità tramite chiamate a <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType> e <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType>.  
  
 Le classi <xref:System.IO.Directory?displayProperty=nameWithType> e <xref:System.IO.File?displayProperty=nameWithType> forniscono metodi statici per il recupero di informazioni su file e directory.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra vari modi per accedere alle informazioni su file e cartelle.  
  
 [!code-csharp[csFilesandFolders#6](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-get-information-about-files-folders-and-drives_1.cs)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Quando si elaborano stringhe di percorso specificate dall'utente, occorre gestire anche le eccezioni per le condizioni seguenti:  
  
-   Il nome file non è valido. Ad esempio, contiene caratteri non validi o solo spazi vuoti.  
  
-   Il nome del file è Null.  
  
-   La lunghezza del nome del file è maggiore della lunghezza massima definita nel sistema.  
  
-   Il nome del file contiene i due punti (:).  
  
 Se l'applicazione non ha autorizzazioni sufficienti per leggere il file specificato, il metodo `Exists` restituisce `false` indipendentemente dal fatto che il percorso esista. Il metodo non genera un'eccezione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO?displayProperty=nameWithType>  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [File system e Registro di sistema (Guida per programmatori C#)](../../../csharp/programming-guide/file-system/index.md)
