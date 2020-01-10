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
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75707857"
---
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a><span data-ttu-id="3e88c-102">Procedura: Eliminare file e directory nello spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="3e88c-102">How to: Delete Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="3e88c-103">È possibile eliminare directory e file all'interno di un file dello spazio di memorizzazione isolato.</span><span class="sxs-lookup"><span data-stu-id="3e88c-103">You can delete directories and files within an isolated storage file.</span></span> <span data-ttu-id="3e88c-104">All'interno di un archivio i nomi di file e directory dipendono dal sistema operativo e vengono specificati come relativi alla radice del file system virtuale.</span><span class="sxs-lookup"><span data-stu-id="3e88c-104">Within a store, file and directory names are operating-system dependent and are specified as relative to the root of the virtual file system.</span></span> <span data-ttu-id="3e88c-105">I nomi non fanno distinzione tra maiuscole e minuscole nei sistemi operativi Windows.</span><span class="sxs-lookup"><span data-stu-id="3e88c-105">They are not case-sensitive on Windows operating systems.</span></span>  
  
 <span data-ttu-id="3e88c-106">La classe <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> fornisce due metodi per eliminare file e directory: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> e <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="3e88c-106">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> class supplies two methods for deleting directories and files: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.</span></span> <span data-ttu-id="3e88c-107">Se si tenta di eliminare un file o una directory che non esiste, viene generata un'eccezione <xref:System.IO.IsolatedStorage.IsolatedStorageException>.</span><span class="sxs-lookup"><span data-stu-id="3e88c-107">An <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown if you try to delete a file or directory that does not exist.</span></span> <span data-ttu-id="3e88c-108">Se si include un carattere jolly nel nome, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> genera un'eccezione <xref:System.IO.IsolatedStorage.IsolatedStorageException> e <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> genera un'eccezione <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="3e88c-108">If you include a wildcard character in the name, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> throws an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception, and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="3e88c-109">Il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> non riesce se la directory contiene file o sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="3e88c-109">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> method fails if the directory contains any files or subdirectories.</span></span> <span data-ttu-id="3e88c-110">È possibile usare i metodi <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> e <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> per recuperare i file e le directory esistenti.</span><span class="sxs-lookup"><span data-stu-id="3e88c-110">You can use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> methods to retrieve the existing files and directories.</span></span> <span data-ttu-id="3e88c-111">Per altre informazioni sulla ricerca nel file system virtuale di un archivio, vedere [Procedura: Trovare file e directory esistenti nello spazio di memorizzazione isolato](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).</span><span class="sxs-lookup"><span data-stu-id="3e88c-111">For more information about searching the virtual file system of a store, see [How to: Find Existing Files and Directories in Isolated Storage](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e88c-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="3e88c-112">Example</span></span>  
 <span data-ttu-id="3e88c-113">L'esempio di codice seguente crea e quindi elimina diversi file e directory.</span><span class="sxs-lookup"><span data-stu-id="3e88c-113">The following code example creates and then deletes several directories and files.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="3e88c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e88c-114">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>
- [<span data-ttu-id="3e88c-115">Spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="3e88c-115">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
