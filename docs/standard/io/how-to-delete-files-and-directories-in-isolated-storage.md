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
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a><span data-ttu-id="ed206-102">Procedura: Eliminare file e directory nello spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="ed206-102">How to: Delete Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="ed206-103">È possibile eliminare le directory e file all'interno di un file di memorizzazione isolato.</span><span class="sxs-lookup"><span data-stu-id="ed206-103">You can delete directories and files within an isolated storage file.</span></span> <span data-ttu-id="ed206-104">All'interno di un archivio, nomi di file e directory sono dipendenti dal sistema operativo e vengono specificati come relativo alla radice del file system virtuale.</span><span class="sxs-lookup"><span data-stu-id="ed206-104">Within a store, file and directory names are operating-system dependent and are specified as relative to the root of the virtual file system.</span></span> <span data-ttu-id="ed206-105">Non sono tra maiuscole e minuscole nei sistemi operativi Windows.</span><span class="sxs-lookup"><span data-stu-id="ed206-105">They are not case-sensitive on Windows operating systems.</span></span>  
  
 <span data-ttu-id="ed206-106">Il <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> classe fornisce due metodi per l'eliminazione di file e directory: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> e <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="ed206-106">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> class supplies two methods for deleting directories and files: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.</span></span> <span data-ttu-id="ed206-107">Un <xref:System.IO.IsolatedStorage.IsolatedStorageException> eccezione viene generata se si tenta di eliminare un file o directory inesistente.</span><span class="sxs-lookup"><span data-stu-id="ed206-107">An <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown if you try to delete a file or directory that does not exist.</span></span> <span data-ttu-id="ed206-108">Se si include un carattere jolly nel nome, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> genera un <xref:System.IO.IsolatedStorage.IsolatedStorageException> eccezione, e <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> genera un <xref:System.ArgumentException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="ed206-108">If you include a wildcard character in the name, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> throws an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception, and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="ed206-109">Il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> metodo ha esito negativo se la directory contiene file o sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="ed206-109">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> method fails if the directory contains any files or subdirectories.</span></span> <span data-ttu-id="ed206-110">È possibile utilizzare il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> e <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> metodi per recuperare il file e directory esistenti.</span><span class="sxs-lookup"><span data-stu-id="ed206-110">You can use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> methods to retrieve the existing files and directories.</span></span> <span data-ttu-id="ed206-111">Per ulteriori informazioni sulla ricerca di file system virtuale di un archivio, vedere [procedura: trovare file e directory esistenti nello spazio di memorizzazione isolato](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).</span><span class="sxs-lookup"><span data-stu-id="ed206-111">For more information about searching the virtual file system of a store, see [How to: Find Existing Files and Directories in Isolated Storage](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed206-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="ed206-112">Example</span></span>  
 <span data-ttu-id="ed206-113">Esempio di codice seguente crea ed Elimina quindi diversi file e directory.</span><span class="sxs-lookup"><span data-stu-id="ed206-113">The following code example creates and then deletes several directories and files.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="ed206-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed206-114">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>  
 [<span data-ttu-id="ed206-115">Spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="ed206-115">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
