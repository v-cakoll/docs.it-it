---
title: 'Procedura: enumerare directory e file'
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
ms.openlocfilehash: 6a26d0ef529b81976c4d2caafed34bb5f08d8d46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75707745"
---
# <a name="how-to-enumerate-directories-and-files"></a>Procedura: enumerare directory e file
Le raccolte enumerabili offrono prestazioni migliori rispetto alle matrici quando si lavora con grandi raccolte di file e directory. Per enumerare directory e file, usare metodi che restituiscono una raccolta enumerabile di nomi di directory o file o dei rispettivi oggetti <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> o <xref:System.IO.FileSystemInfo>.  
  
Se si vogliono cercare e restituire solo i nomi di directory o file, usare i metodi di enumerazione della classe <xref:System.IO.Directory>. Se si vogliono cercare e restituire altre proprietà di directory o file, usare le classi <xref:System.IO.DirectoryInfo> e <xref:System.IO.FileSystemInfo>.  
  
È possibile usare raccolte enumerabili ottenute da questi metodi come parametro <xref:System.Collections.Generic.IEnumerable%601> per i costruttori di classi di raccolte, come <xref:System.Collections.Generic.List%601>.  
  
La tabella seguente riepiloga i metodi che restituiscono raccolte enumerabili di file e directory:  
  
|Per cercare e restituire|Usare il metodo|  
|------------------|-------------------------------------|-------------------|  
|Nomi di directory|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|Informazioni sulle directory (<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|Nomi file|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Informazioni sui file (<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Nomi di voci del file system|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
|Informazioni sulle voci di file system (<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
|Nomi di file e directory |<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  

> [!NOTE]
> Anche se è possibile enumerare immediatamente tutti i file presenti nelle sottodirectory della directory padre usando l'opzione <xref:System.IO.SearchOption.AllDirectories> dell'enumerazione <xref:System.IO.SearchOption> facoltativa, errori <xref:System.UnauthorizedAccessException> possono rendere incompleta l'enumerazione. È possibile intercettare queste eccezioni enumerando prima di tutto le directory e quindi i file.  
  
## <a name="examples-use-the-directory-class"></a>Esempi: utilizzare la classe Directory  
  
L'esempio seguente usa il metodo <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> per ottenere un elenco dei nomi delle directory di primo livello in un percorso specificato.  

[!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
[!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  

L'esempio seguente usa il metodo <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> per enumerare in modo ricorsivo tutti i nomi file in una directory e nelle relative sottodirectory che soddisfano un criterio specifico. L'esempio legge quindi ogni riga di ogni file e visualizza le righe che contengono una stringa specificata, con i nomi file e i percorsi corrispondenti.

[!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
[!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
## <a name="examples-use-the-directoryinfo-class"></a>Esempi: utilizzare la classe DirectoryInfo  
  
L'esempio seguente usa il metodo <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> per elencare una raccolta di directory di primo livello la cui proprietà <xref:System.IO.FileSystemInfo.CreationTimeUtc> è precedente a un valore <xref:System.DateTime> specifico.  

[!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs)]
[!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb)]  
  
L'esempio seguente usa il metodo <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> per elencare tutti i file la cui proprietà <xref:System.IO.FileInfo.Length> supera i 10 MB. Questo esempio enumera prima di tutto le directory di primo livello per intercettare possibili eccezioni di accesso non autorizzato e quindi enumera i file.  

[!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
[!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [I/O di file e di flussi](../../../docs/standard/io/index.md)
