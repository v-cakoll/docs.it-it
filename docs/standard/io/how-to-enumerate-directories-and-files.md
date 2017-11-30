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
helpviewer_keywords: I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: caf9bdec017a5466269ff7fe97be4d0243035b4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-directories-and-files"></a>Procedura: enumerare directory e file
È possibile enumerare directory e file utilizzando i metodi che restituiscono una raccolta enumerabile di stringhe dei nomi. È inoltre possibile utilizzare i metodi che restituiscono una raccolta enumerabile di <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, o <xref:System.IO.FileSystemInfo> oggetti. Raccolte enumerabili offrono prestazioni migliori rispetto alle matrici quando si lavora con grandi raccolte di file e directory.  
  
 È inoltre possibile utilizzare raccolte enumerabili ottenute da questi metodi per fornire il <xref:System.Collections.Generic.IEnumerable%601> parametro per i costruttori di raccolta di classi quali la <xref:System.Collections.Generic.List%601> classe.  
  
 Se si desidera ottenere solo i nomi di directory o file, utilizzare i metodi di enumerazione del <xref:System.IO.Directory> classe. Se si desidera ottenere altre proprietà delle directory o file, utilizzare il <xref:System.IO.DirectoryInfo> e <xref:System.IO.FileSystemInfo> classi.  
  
 Nella tabella seguente viene fornita una Guida per i metodi che restituiscono raccolte enumerabili.  
  
|Per enumerare|Raccolta enumerabile da restituire|Metodo da utilizzare|  
|------------------|-------------------------------------|-------------------|  
|Directory|Nomi di directory|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||Informazioni sulla directory (<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|File|Nomi file|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||Informazioni sui file (<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Informazioni sul file system|Voci del file di sistema|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||Informazioni sul file system (<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 Anche se è possibile enumerare tutti i file presenti nelle sottodirectory della directory padre immediatamente tramite il <xref:System.IO.SearchOption.AllDirectories> fornito dall'opzione di ricerca di <xref:System.IO.SearchOption> enumerazione, le eccezioni di accesso non autorizzato (<xref:System.UnauthorizedAccessException>) potrebbe causare un'enumerazione che non siano completi. Se queste eccezioni sono possibili, è possibile intercettarle e continuare prima l'enumerazione di directory e quindi l'enumerazione dei file.  
  
### <a name="to-enumerate-directory-names"></a>Per enumerare i nomi di directory  
  
-   Utilizzare il <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> per ottenere un elenco dei nomi di directory di primo livello in un percorso specificato.  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a>Per enumerare i nomi di file in una directory e sottodirectory  
  
-   Utilizzare il <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> metodo per la ricerca di una directory e (facoltativamente) nelle relative sottodirectory e per ottenere un elenco di nomi di file che corrispondono a un criterio di ricerca specificati.  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a>Per enumerare una raccolta di oggetti DirectoryInfo  
  
-   Utilizzare il <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> per ottenere una raccolta di directory di primo livello.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a>Per enumerare una raccolta di oggetti FileInfo in tutte le directory  
  
-   Utilizzare il <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> per ottenere una raccolta di file che corrispondono a un criterio di ricerca specificati in tutte le directory. In questo esempio viene innanzitutto enumera la directory di primo livello per intercettare le eccezioni di accesso non autorizzato possibili e quindi enumera i file.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [I/O di file e di flussi](../../../docs/standard/io/index.md)
