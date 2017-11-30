---
title: 'Procedura: Trovare file e directory esistenti nello spazio di memorizzazione isolato'
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
- stores, finding files and directories
- locating files in isolated storage file
- directories [.NET Framework], isolated storage
- isolated storage, finding files and directories
- data storage using isolated storage, finding files and directories
- files [.NET Framework], isolated storage
- data stores, finding files and directories
- locating directories in isolated storage file
- storing data using isolated storage, finding files and directories
ms.assetid: eb28458a-6161-4e7a-9ada-30ef93761b5c
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 656c390358b6f6a671cf3ef11ea7be75f897d21c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-existing-files-and-directories-in-isolated-storage"></a>Procedura: Trovare file e directory esistenti nello spazio di memorizzazione isolato
Per cercare una directory nell'archiviazione isolata, utilizzare il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType> metodo. Questo metodo accetta una stringa che rappresenta un criterio di ricerca. È possibile utilizzare sia un solo carattere (?) e più caratteri (*) i caratteri jolly nel criterio di ricerca, ma i caratteri jolly devono essere visualizzato nella parte finale del nome. Ad esempio, `directory1/*ect*` è una stringa di ricerca valido, ma `*ect*/directory2` non.  
  
 Per cercare un file, utilizzare il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType> metodo. La restrizione dei caratteri jolly in stringhe di ricerca che si applica a <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> si applica anche alle <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.  
  
 Nessuno di questi metodi è ricorsiva; la <xref:System.IO.IsolatedStorage.IsolatedStorageFile> classe non fornisce metodi per elencare tutte le directory o file nell'archivio. Tuttavia, i metodi di ricorsive sono illustrati nell'esempio di codice seguente.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come creare file e directory in un archivio isolato. In primo luogo, cui viene recuperato e inserito in un archivio isolato per utente, dominio e assembly di `isoStore` variabile. Il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> metodo viene utilizzato per impostare le directory e <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> costruttore crea alcuni file in tali directory. Il codice consente quindi di scorrere i risultati del `GetAllDirectories` metodo. Questo metodo utilizza <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> per trovare tutti i nomi di directory nella directory corrente. Questi nomi vengono archiviati in una matrice e quindi `GetAllDirectories` chiama se stessa, passando ogni directory che è stato individuato. Di conseguenza, tutti i nomi delle directory vengono restituiti in una matrice. Successivamente, il codice chiama il `GetAllFiles` metodo. Questo metodo chiama `GetAllDirectories` per trovare i nomi di tutte le directory e quindi controlla ogni directory per i file usando il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> metodo. Il risultato viene restituito in una matrice per la visualizzazione.  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [Spazio di memorizzazione isolato](../../../docs/standard/io/isolated-storage.md)
