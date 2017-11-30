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
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a><span data-ttu-id="b8a0a-102">Procedura: Creare file e directory nello spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="b8a0a-102">How to: Create Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="b8a0a-103">Dopo aver ottenuto un archivio isolato, è possibile creare una directory e file per l'archiviazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="b8a0a-103">After you have obtained an isolated store, you can create directories and files for storing data.</span></span> <span data-ttu-id="b8a0a-104">All'interno di un archivio, vengono specificati nomi di file e directory rispetto alla radice del file system virtuale.</span><span class="sxs-lookup"><span data-stu-id="b8a0a-104">Within a store, file and directory names are specified with respect to the root of the virtual file system.</span></span>  
  
 <span data-ttu-id="b8a0a-105">Per creare una directory, utilizzare il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> metodo di istanza.</span><span class="sxs-lookup"><span data-stu-id="b8a0a-105">To create a directory, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="b8a0a-106">Se si specifica una sottodirectory della directory che non esiste, entrambe le directory vengono create.</span><span class="sxs-lookup"><span data-stu-id="b8a0a-106">If you specify a subdirectory of an directory that doesn't exist, both directories are created.</span></span> <span data-ttu-id="b8a0a-107">Se si specifica una directory già esistente, il metodo restituisce senza creare una directory e viene generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="b8a0a-107">If you specify a directory that already exists, the method returns without creating a directory, and no exception is thrown.</span></span> <span data-ttu-id="b8a0a-108">Tuttavia, se si specifica un nome di directory che contiene caratteri non validi, un <xref:System.IO.IsolatedStorage.IsolatedStorageException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b8a0a-108">However, if you specify a directory name that contains invalid characters, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown.</span></span>  
  
 <span data-ttu-id="b8a0a-109">Per creare un file, utilizzare il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b8a0a-109">To create a file, use  the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="b8a0a-110">Nel sistema operativo Windows, di memorizzazione isolato file e directory, i nomi sono tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="b8a0a-110">In the Windows operating system, isolated storage file and directory names are case-insensitive.</span></span> <span data-ttu-id="b8a0a-111">Ovvero, se si crea un file denominato `ThisFile.txt`e quindi creare un file denominato `THISFILE.TXT`, viene creato un solo file.</span><span class="sxs-lookup"><span data-stu-id="b8a0a-111">That is, if you create a file named `ThisFile.txt`, and then create another file named `THISFILE.TXT`, only one file is created.</span></span> <span data-ttu-id="b8a0a-112">Il nome del file mantiene il relativo originale maiuscole e minuscole ai fini della visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b8a0a-112">The file name keeps its original casing for display purposes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8a0a-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8a0a-113">Example</span></span>  
 <span data-ttu-id="b8a0a-114">Esempio di codice seguente viene illustrato come creare file e directory in un archivio isolato.</span><span class="sxs-lookup"><span data-stu-id="b8a0a-114">The following code example illustrates how to create files and directories in an isolated store.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b8a0a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8a0a-115">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 [<span data-ttu-id="b8a0a-116">Spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="b8a0a-116">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
