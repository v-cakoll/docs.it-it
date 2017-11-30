---
title: 'Procedura: Creare file e directory nello spazio di memorizzazione isolato'
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
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, creating files and directories
- data stores, creating files and directories
- data storage using isolated storage, creating files and directories
- stores, creating files and directories
- storing data using isolated storage, creating files and directories
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b8a48473bf9ac91b89657d00d27031255491353
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a>Procedura: Creare file e directory nello spazio di memorizzazione isolato
Dopo aver ottenuto un archivio isolato, è possibile creare una directory e file per l'archiviazione dei dati. All'interno di un archivio, vengono specificati nomi di file e directory rispetto alla radice del file system virtuale.  
  
 Per creare una directory, utilizzare il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> metodo di istanza. Se si specifica una sottodirectory della directory che non esiste, entrambe le directory vengono create. Se si specifica una directory già esistente, il metodo restituisce senza creare una directory e viene generata alcuna eccezione. Tuttavia, se si specifica un nome di directory che contiene caratteri non validi, un <xref:System.IO.IsolatedStorage.IsolatedStorageException> viene generata un'eccezione.  
  
 Per creare un file, utilizzare il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType>.  
  
 Nel sistema operativo Windows, di memorizzazione isolato file e directory, i nomi sono tra maiuscole e minuscole. Ovvero, se si crea un file denominato `ThisFile.txt`e quindi creare un file denominato `THISFILE.TXT`, viene creato un solo file. Il nome del file mantiene il relativo originale maiuscole e minuscole ai fini della visualizzazione.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come creare file e directory in un archivio isolato.  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 [Spazio di memorizzazione isolato](../../../docs/standard/io/isolated-storage.md)
