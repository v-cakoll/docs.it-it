---
title: 'Procedura: Trovare file e directory esistenti nello spazio di memorizzazione isolato'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: dfebcc9acf0b699f898c106921d15ce0294bc5d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75707133"
---
# <a name="how-to-find-existing-files-and-directories-in-isolated-storage"></a>Procedura: Trovare file e directory esistenti nello spazio di memorizzazione isolato

Per cercare una directory nello spazio di memorizzazione isolato, usare il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType>. Questo metodo accetta una stringa che rappresenta un criterio di ricerca. Nel criterio di ricerca è possibile usare sia un solo carattere jolly (?) sia più caratteri jolly (\*), ma questi devono trovarsi nella parte finale del nome. Ad esempio, `directory1/*ect*` è una stringa di ricerca valida, mentre `*ect*/directory2` non lo è.  
  
 Per cercare un file, usare il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType>. La restrizione relativa ai caratteri jolly nelle stringhe di ricerca applicata a <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> si applica anche a <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.  
  
 Nessuno di questi metodi è ricorsivo. La classe <xref:System.IO.IsolatedStorage.IsolatedStorageFile> non fornisce alcun metodo per elencare tutti file o le directory nell'archivio. Tuttavia, i metodi ricorsivi vengono mostrati nell'esempio di codice seguente.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente mostra come creare file e directory in uno spazio di memorizzazione isolato. Prima di tutto, viene recuperato uno spazio di memorizzazione isolato in base all'utente, al dominio e all'assembly, che viene inserito nella variabile `isoStore`. Viene usato il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> per configurare alcune directory diverse e il costruttore <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> crea alcuni file in queste directory. Il codice esegue quindi il ciclo nei risultati del metodo `GetAllDirectories`. Questo metodo usa <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> per trovare tutti i nomi di directory nella directory corrente. Questi nomi vengono archiviati in una matrice e quindi il metodo `GetAllDirectories` chiama se stesso, passando ogni directory trovata. Come risultato, vengono restituiti tutti i nomi di directory in una matrice. Il codice chiama quindi il metodo `GetAllFiles`. Questo metodo chiama `GetAllDirectories` per trovare i nomi di tutte le directory e quindi controlla ogni directory per individuare i file usando il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>. Il risultato viene restituito in una matrice per la visualizzazione.  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [Archiviazione isolata](../../../docs/standard/io/isolated-storage.md)
