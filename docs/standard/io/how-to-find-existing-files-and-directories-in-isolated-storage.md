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
# <a name="how-to-find-existing-files-and-directories-in-isolated-storage"></a><span data-ttu-id="7d00b-102">Procedura: Trovare file e directory esistenti nello spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="7d00b-102">How to: Find Existing Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="7d00b-103">Per cercare una directory nell'archiviazione isolata, utilizzare il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="7d00b-103">To search for a directory in isolated storage, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7d00b-104">Questo metodo accetta una stringa che rappresenta un criterio di ricerca.</span><span class="sxs-lookup"><span data-stu-id="7d00b-104">This method takes a string that represents a search pattern.</span></span> <span data-ttu-id="7d00b-105">È possibile utilizzare sia un solo carattere (?) e più caratteri (*) i caratteri jolly nel criterio di ricerca, ma i caratteri jolly devono essere visualizzato nella parte finale del nome.</span><span class="sxs-lookup"><span data-stu-id="7d00b-105">You can use both single-character (?) and multi-character (*) wildcard characters in the search pattern, but the wildcard characters must appear in the final portion of the name.</span></span> <span data-ttu-id="7d00b-106">Ad esempio, `directory1/*ect*` è una stringa di ricerca valido, ma `*ect*/directory2` non.</span><span class="sxs-lookup"><span data-stu-id="7d00b-106">For example, `directory1/*ect*` is a valid search string, but `*ect*/directory2` is not.</span></span>  
  
 <span data-ttu-id="7d00b-107">Per cercare un file, utilizzare il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="7d00b-107">To search for a file, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7d00b-108">La restrizione dei caratteri jolly in stringhe di ricerca che si applica a <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> si applica anche alle <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.</span><span class="sxs-lookup"><span data-stu-id="7d00b-108">The restriction for wildcard characters in search strings that applies to <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> also applies to <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.</span></span>  
  
 <span data-ttu-id="7d00b-109">Nessuno di questi metodi è ricorsiva; la <xref:System.IO.IsolatedStorage.IsolatedStorageFile> classe non fornisce metodi per elencare tutte le directory o file nell'archivio.</span><span class="sxs-lookup"><span data-stu-id="7d00b-109">Neither of these methods is recursive; the <xref:System.IO.IsolatedStorage.IsolatedStorageFile> class does not supply any methods for listing all directories or files in your store.</span></span> <span data-ttu-id="7d00b-110">Tuttavia, i metodi di ricorsive sono illustrati nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7d00b-110">However, recursive methods are shown in the following code example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d00b-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d00b-111">Example</span></span>  
 <span data-ttu-id="7d00b-112">Esempio di codice seguente viene illustrato come creare file e directory in un archivio isolato.</span><span class="sxs-lookup"><span data-stu-id="7d00b-112">The following code example illustrates how to create files and directories in an isolated store.</span></span> <span data-ttu-id="7d00b-113">In primo luogo, cui viene recuperato e inserito in un archivio isolato per utente, dominio e assembly di `isoStore` variabile.</span><span class="sxs-lookup"><span data-stu-id="7d00b-113">First, a store that is isolated for user, domain, and assembly is retrieved and placed in the `isoStore` variable.</span></span> <span data-ttu-id="7d00b-114">Il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> metodo viene utilizzato per impostare le directory e <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> costruttore crea alcuni file in tali directory.</span><span class="sxs-lookup"><span data-stu-id="7d00b-114">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> method is used to set up a few different directories, and the <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> constructor creates some files in these directories.</span></span> <span data-ttu-id="7d00b-115">Il codice consente quindi di scorrere i risultati del `GetAllDirectories` metodo.</span><span class="sxs-lookup"><span data-stu-id="7d00b-115">The code then loops through the results of the `GetAllDirectories` method.</span></span> <span data-ttu-id="7d00b-116">Questo metodo utilizza <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> per trovare tutti i nomi di directory nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="7d00b-116">This method uses <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> to find all the directory names in the current directory.</span></span> <span data-ttu-id="7d00b-117">Questi nomi vengono archiviati in una matrice e quindi `GetAllDirectories` chiama se stessa, passando ogni directory che è stato individuato.</span><span class="sxs-lookup"><span data-stu-id="7d00b-117">These names are stored in an array, and then `GetAllDirectories` calls itself, passing in each directory it has found.</span></span> <span data-ttu-id="7d00b-118">Di conseguenza, tutti i nomi delle directory vengono restituiti in una matrice.</span><span class="sxs-lookup"><span data-stu-id="7d00b-118">As a result, all the directory names are returned in an array.</span></span> <span data-ttu-id="7d00b-119">Successivamente, il codice chiama il `GetAllFiles` metodo.</span><span class="sxs-lookup"><span data-stu-id="7d00b-119">Next, the code calls the `GetAllFiles` method.</span></span> <span data-ttu-id="7d00b-120">Questo metodo chiama `GetAllDirectories` per trovare i nomi di tutte le directory e quindi controlla ogni directory per i file usando il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="7d00b-120">This method calls `GetAllDirectories` to find out the names of all the directories, and then it checks each directory for files by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> method.</span></span> <span data-ttu-id="7d00b-121">Il risultato viene restituito in una matrice per la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7d00b-121">The result is returned in an array for display.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="7d00b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d00b-122">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [<span data-ttu-id="7d00b-123">Spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="7d00b-123">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
