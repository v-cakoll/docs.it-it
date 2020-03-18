---
title: 'Procedura: Eliminare file e directory nello spazio di memorizzazione isolato'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: ec4de3e3a139cfcf66f1f6252c03c467f4ccfbc5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75707857"
---
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a>Procedura: Eliminare file e directory nello spazio di memorizzazione isolato
È possibile eliminare directory e file all'interno di un file dello spazio di memorizzazione isolato. All'interno di un archivio i nomi di file e directory dipendono dal sistema operativo e vengono specificati come relativi alla radice del file system virtuale. I nomi non fanno distinzione tra maiuscole e minuscole nei sistemi operativi Windows.  
  
 La classe <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> fornisce due metodi per eliminare file e directory: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> e <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>. Se si tenta di eliminare un file o una directory che non esiste, viene generata un'eccezione <xref:System.IO.IsolatedStorage.IsolatedStorageException>. Se si include un carattere jolly nel nome, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> genera un'eccezione <xref:System.IO.IsolatedStorage.IsolatedStorageException> e <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> genera un'eccezione <xref:System.ArgumentException>.  
  
 Il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> non riesce se la directory contiene file o sottodirectory. È possibile usare i metodi <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> e <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> per recuperare i file e le directory esistenti. Per altre informazioni sulla ricerca nel file system virtuale di un archivio, vedere [Procedura: Trovare file e directory esistenti nello spazio di memorizzazione isolato](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente crea e quindi elimina diversi file e directory.  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>
- [Archiviazione isolata](../../../docs/standard/io/isolated-storage.md)
