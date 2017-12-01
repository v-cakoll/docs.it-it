---
title: 'Procedura: Eliminare file e directory nello spazio di memorizzazione isolato'
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
- cpp
helpviewer_keywords:
- data storage using isolated storage, deleting files and directories
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, deleting files and directories
- data stores, deleting files and directories
- stores, creating files and directories
- deleting files within isolated stage file
- storing data using isolated storage, deleting files and directories
- deleting directories within isolated stage file
ms.assetid: 8fcc0dea-435b-4d40-ba4d-ba056265c202
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 971f27cd25cbe4be3ca3fad6283ab32d4f6db0ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a>Procedura: Eliminare file e directory nello spazio di memorizzazione isolato
È possibile eliminare le directory e file all'interno di un file di memorizzazione isolato. All'interno di un archivio, nomi di file e directory sono dipendenti dal sistema operativo e vengono specificati come relativo alla radice del file system virtuale. Non sono tra maiuscole e minuscole nei sistemi operativi Windows.  
  
 Il <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> classe fornisce due metodi per l'eliminazione di file e directory: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> e <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>. Un <xref:System.IO.IsolatedStorage.IsolatedStorageException> eccezione viene generata se si tenta di eliminare un file o directory inesistente. Se si include un carattere jolly nel nome, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> genera un <xref:System.IO.IsolatedStorage.IsolatedStorageException> eccezione, e <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> genera un <xref:System.ArgumentException> eccezione.  
  
 Il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> metodo ha esito negativo se la directory contiene file o sottodirectory. È possibile utilizzare il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> e <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> metodi per recuperare il file e directory esistenti. Per ulteriori informazioni sulla ricerca di file system virtuale di un archivio, vedere [procedura: trovare file e directory esistenti nello spazio di memorizzazione isolato](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente crea ed Elimina quindi diversi file e directory.  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>  
 [Spazio di memorizzazione isolato](../../../docs/standard/io/isolated-storage.md)
