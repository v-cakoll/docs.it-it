---
title: 'Procedura: enumerare directory e file'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5d0f22853210144881e49c4192ea38a5c3e57cda
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-enumerate-directories-and-files"></a>Procedura: enumerare directory e file
È possibile enumerare directory e file usando i metodi che restituiscono una raccolta enumerabile di stringhe dei rispettivi nomi. È anche possibile usare metodi che restituiscono una raccolta enumerabile di oggetti <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> o <xref:System.IO.FileSystemInfo>. Le raccolte enumerabili offrono prestazioni migliori rispetto alle matrici quando si lavora con grandi raccolte di file e directory.  
  
 È anche possibile usare raccolte enumerabili ottenute da questi metodi per fornire il parametro <xref:System.Collections.Generic.IEnumerable%601> per i costruttori di classi di raccolte, ad esempio la classe <xref:System.Collections.Generic.List%601>.  
  
 Se si vuole ottenere solo i nomi di directory o file, usare i metodi di enumerazione della classe <xref:System.IO.Directory>. Se si vuole ottenere altre proprietà di directory o file, usare le classi <xref:System.IO.DirectoryInfo> e <xref:System.IO.FileSystemInfo>.  
  
 La tabella seguente offre una guida ai metodi che restituiscono raccolte enumerabili.  
  
|Per enumerare|Raccolta enumerabile da restituire|Metodo da usare|  
|------------------|-------------------------------------|-------------------|  
|Directory|Nomi di directory|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||Informazioni sulle directory (<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|File|Nomi file|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||Informazioni sui file (<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Informazioni sui file system|Voci di file system|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||Informazioni sui file system (<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 Anche se è possibile enumerare immediatamente tutti i file presenti nelle sottodirectory della directory padre usando l'opzione di ricerca <xref:System.IO.SearchOption.AllDirectories> fornita dall'enumerazione <xref:System.IO.SearchOption>, eccezioni di accesso non autorizzato (<xref:System.UnauthorizedAccessException>) possono fare sì che l'enumerazione non sia completa. Se queste eccezioni sono possibili, è possibile intercettarle e continuare enumerando prima di tutto le directory e quindi i file.  
  
### <a name="to-enumerate-directory-names"></a>Per enumerare nomi di directory  
  
-   Usare il metodo <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> per ottenere un elenco dei nomi di directory di primo livello in un percorso specificato.  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a>Per enumerare nomi di file in una directory e in sottodirectory  
  
-   Usare il metodo <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> per cercare in una directory e (facoltativamente) nelle relative sottodirectory e ottenere un elenco di nomi di file che corrispondono a un criterio di ricerca specificato.  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a>Per enumerare una raccolta di oggetti DirectoryInfo  
  
-   Usare il metodo <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> per ottenere una raccolta di directory di primo livello.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a>Per enumerare una raccolta di oggetti FileInfo in tutte le directory  
  
-   Usare il metodo <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> per ottenere una raccolta di file che corrispondono a un criterio di ricerca specificato in tutte le directory. Questo esempio enumera prima di tutto le directory di primo livello per intercettare le possibili eccezioni di accesso non autorizzato e quindi enumera i file.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [I/O di file e di flussi](../../../docs/standard/io/index.md)
