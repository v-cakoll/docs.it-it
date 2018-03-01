---
title: 'Procedura: leggere e scrivere sui file nello spazio di memorizzazione isolato'
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
- files, isolated storage
- reading data
- storing data using isolated storage, reading and writing to files
- writing to files within store
- data storage using isolated storage, reading and writing to files
- reading files within store
- isolated storage, reading and writing to files
- data stores, reading and writing to files
- stores, reading and writing to files
ms.assetid: f977ebdc-1b55-475a-bc3d-3376470b08ae
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cfb1500150d2dfb500a698713c0de6b8e5518010
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-read-and-write-to-files-in-isolated-storage"></a>Procedura: leggere e scrivere sui file nello spazio di memorizzazione isolato
Per leggere da un file in un archivio isolato o scrivervi, utilizzare un oggetto <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> con un lettore di flusso (oggetto <xref:System.IO.StreamReader>) o uno scrittore di flusso (oggetto <xref:System.IO.StreamWriter>).  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente ottiene un archivio isolato e controlla se nell'archivio è presente un file denominato TestStore.txt. Se non è presente, crea il file e scrive "Hello Isolated Storage" al suo interno. Se il file TestStore.txt è presente, l'esempio di codice legge dal file.  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 <xref:System.IO.FileMode?displayProperty=nameWithType>  
 <xref:System.IO.FileAccess?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader?displayProperty=nameWithType>  
 <xref:System.IO.StreamWriter?displayProperty=nameWithType>  
 [I/O di file e di flussi](../../../docs/standard/io/index.md)  
 [Spazio di memorizzazione isolato](../../../docs/standard/io/isolated-storage.md)
