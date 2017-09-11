---
title: File system e Registro di sistema (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6a9130fa666f8b2bce7762c5bd4a8b263d619aba
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="7cb0d-102">File system e Registro di sistema (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7cb0d-102">File System and the Registry (C# Programming Guide)</span></span>
<span data-ttu-id="7cb0d-103">Gli argomenti seguenti illustrano come usare C# e .NET Framework per eseguire varie operazioni di base su file e cartelle e nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="7cb0d-103">The following topics show how to use C# and the .NET Framework to perform various basic operations on files, folders, and the Registry.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7cb0d-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="7cb0d-104">In This Section</span></span>  
  
|<span data-ttu-id="7cb0d-105">**Titolo**</span><span class="sxs-lookup"><span data-stu-id="7cb0d-105">**Title**</span></span>|<span data-ttu-id="7cb0d-106">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7cb0d-106">**Description**</span></span>|  
|---------------|---------------------|  
|[<span data-ttu-id="7cb0d-107">Procedura: Scorrere un albero di directory</span><span class="sxs-lookup"><span data-stu-id="7cb0d-107">How to: Iterate Through a Directory Tree</span></span>](../../../csharp/programming-guide/file-system/how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="7cb0d-108">Viene mostrato come scorrere manualmente una struttura ad albero di directory.</span><span class="sxs-lookup"><span data-stu-id="7cb0d-108">Shows how to manually iterate through a directory tree.</span></span>|  
|[<span data-ttu-id="7cb0d-109">Procedura: Ottenere informazioni relative a file, cartelle e unità</span><span class="sxs-lookup"><span data-stu-id="7cb0d-109">How to: Get Information About Files, Folders, and Drives</span></span>](../../../csharp/programming-guide/file-system/how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="7cb0d-110">Viene mostrato come recuperare informazioni relative a file, cartelle e unità, ad esempio la data di creazione e la dimensione.</span><span class="sxs-lookup"><span data-stu-id="7cb0d-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|  
|[<span data-ttu-id="7cb0d-111">Procedura: Creare un file o una cartella</span><span class="sxs-lookup"><span data-stu-id="7cb0d-111">How to: Create a File or Folder</span></span>](../../../csharp/programming-guide/file-system/how-to-create-a-file-or-folder.md)|<span data-ttu-id="7cb0d-112">Viene mostrato come creare un nuovo file o una nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="7cb0d-112">Shows how to create a new file or folder.</span></span>|  
|[<span data-ttu-id="7cb0d-113">Procedura: Copiare, eliminare e spostare file e cartelle (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7cb0d-113">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="7cb0d-114">Viene mostrato come copiare, eliminare e spostare file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="7cb0d-114">Shows how to copy, delete and move files and folders.</span></span>|  
|[<span data-ttu-id="7cb0d-115">Procedura: Creare una finestra di dialogo dello stato di avanzamento per operazioni su file</span><span class="sxs-lookup"><span data-stu-id="7cb0d-115">How to: Provide a Progress Dialog Box for File Operations</span></span>](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="7cb0d-116">Viene mostrato come visualizzare una finestra di stato Windows standard per determinate operazioni sui file.</span><span class="sxs-lookup"><span data-stu-id="7cb0d-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|  
|[<span data-ttu-id="7cb0d-117">Procedura: Scrivere in un file di testo</span><span class="sxs-lookup"><span data-stu-id="7cb0d-117">How to: Write to a Text File</span></span>](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md)|<span data-ttu-id="7cb0d-118">Viene mostrato come scrivere in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="7cb0d-118">Shows how to write to a text file.</span></span>|  
|[<span data-ttu-id="7cb0d-119">Procedura: Leggere da un file di testo</span><span class="sxs-lookup"><span data-stu-id="7cb0d-119">How to: Read From a Text File</span></span>](../../../csharp/programming-guide/file-system/how-to-read-from-a-text-file.md)|<span data-ttu-id="7cb0d-120">Viene mostrato come leggere da un file di testo.</span><span class="sxs-lookup"><span data-stu-id="7cb0d-120">Shows how to read from a text file.</span></span>|  
|[<span data-ttu-id="7cb0d-121">Procedura: Leggere un file di testo una riga alla volta</span><span class="sxs-lookup"><span data-stu-id="7cb0d-121">How to: Read a Text File One Line at a Time</span></span>](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="7cb0d-122">Viene mostrato come recuperare testo da un file una riga alla volta.</span><span class="sxs-lookup"><span data-stu-id="7cb0d-122">Shows how to retrieve text from a file one line at a time.</span></span>|  
|[<span data-ttu-id="7cb0d-123">Procedura: Creare una chiave nel Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="7cb0d-123">How to: Create a Key In the Registry</span></span>](../../../csharp/programming-guide/file-system/how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="7cb0d-124">Viene mostrato come scrivere una chiave nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="7cb0d-124">Shows how to write a key to the system registry.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="7cb0d-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="7cb0d-125">Related Sections</span></span>  
 [<span data-ttu-id="7cb0d-126">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="7cb0d-126">File and Stream I/O</span></span>](https://msdn.microsoft.com/library/k3352a4t)  
  
 [<span data-ttu-id="7cb0d-127">Procedura: Copiare, eliminare e spostare file e cartelle (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7cb0d-127">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/how-to-copy-delete-and-move-files-and-folders.md)  
  
 [<span data-ttu-id="7cb0d-128">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7cb0d-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
  
 <span data-ttu-id="7cb0d-129">[Files, Folders and Drives](../../../csharp/programming-guide/file-system/index.md) (File, cartelle e unità)</span><span class="sxs-lookup"><span data-stu-id="7cb0d-129">[Files, Folders and Drives](../../../csharp/programming-guide/file-system/index.md)</span></span>  
  
 <xref:System.IO?displayProperty=fullName>

