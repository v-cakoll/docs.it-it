---
title: File system e Registro di sistema - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: 2540c816a102a7f11f1f103b993194cccf0f4688
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75704521"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="21ddf-102">File system e Registro di sistema (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="21ddf-102">File System and the Registry (C# Programming Guide)</span></span>
<span data-ttu-id="21ddf-103">Gli argomenti seguenti illustrano come usare C# e .NET Framework per eseguire varie operazioni di base su file e cartelle e nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="21ddf-103">The following topics show how to use C# and the .NET Framework to perform various basic operations on files, folders, and the Registry.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="21ddf-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="21ddf-104">In This Section</span></span>  
  
|<span data-ttu-id="21ddf-105">**Titolo**</span><span class="sxs-lookup"><span data-stu-id="21ddf-105">**Title**</span></span>|<span data-ttu-id="21ddf-106">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="21ddf-106">**Description**</span></span>|  
|---------------|---------------------|  
|[<span data-ttu-id="21ddf-107">Come scorrere un albero di directory</span><span class="sxs-lookup"><span data-stu-id="21ddf-107">How to iterate through a directory tree</span></span>](./how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="21ddf-108">Viene mostrato come scorrere manualmente una struttura ad albero di directory.</span><span class="sxs-lookup"><span data-stu-id="21ddf-108">Shows how to manually iterate through a directory tree.</span></span>|  
|[<span data-ttu-id="21ddf-109">Come ottenere informazioni su file, cartelle e unità</span><span class="sxs-lookup"><span data-stu-id="21ddf-109">How to get information about files, folders, and drives</span></span>](./how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="21ddf-110">Viene mostrato come recuperare informazioni relative a file, cartelle e unità, ad esempio la data di creazione e la dimensione.</span><span class="sxs-lookup"><span data-stu-id="21ddf-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|  
|[<span data-ttu-id="21ddf-111">Come creare un file o una cartella</span><span class="sxs-lookup"><span data-stu-id="21ddf-111">How to create a file or folder</span></span>](./how-to-create-a-file-or-folder.md)|<span data-ttu-id="21ddf-112">Viene mostrato come creare un nuovo file o una nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="21ddf-112">Shows how to create a new file or folder.</span></span>|  
|[<span data-ttu-id="21ddf-113">Come copiare, eliminare e spostare file e cartelle (C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="21ddf-113">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](./how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="21ddf-114">Viene mostrato come copiare, eliminare e spostare file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="21ddf-114">Shows how to copy, delete and move files and folders.</span></span>|  
|[<span data-ttu-id="21ddf-115">Come specificare una finestra di dialogo di stato per le operazioni su file</span><span class="sxs-lookup"><span data-stu-id="21ddf-115">How to provide a progress dialog box for file operations</span></span>](./how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="21ddf-116">Viene mostrato come visualizzare una finestra di stato Windows standard per determinate operazioni sui file.</span><span class="sxs-lookup"><span data-stu-id="21ddf-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|  
|[<span data-ttu-id="21ddf-117">Come scrivere in un file di testo</span><span class="sxs-lookup"><span data-stu-id="21ddf-117">How to write to a text file</span></span>](./how-to-write-to-a-text-file.md)|<span data-ttu-id="21ddf-118">Viene mostrato come scrivere in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="21ddf-118">Shows how to write to a text file.</span></span>|  
|[<span data-ttu-id="21ddf-119">Come leggere da un file di testo</span><span class="sxs-lookup"><span data-stu-id="21ddf-119">How to read from a text file</span></span>](./how-to-read-from-a-text-file.md)|<span data-ttu-id="21ddf-120">Viene mostrato come leggere da un file di testo.</span><span class="sxs-lookup"><span data-stu-id="21ddf-120">Shows how to read from a text file.</span></span>|  
|[<span data-ttu-id="21ddf-121">Come leggere un file di testo una riga alla volta</span><span class="sxs-lookup"><span data-stu-id="21ddf-121">How to read a text file one line at a time</span></span>](./how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="21ddf-122">Viene mostrato come recuperare testo da un file una riga alla volta.</span><span class="sxs-lookup"><span data-stu-id="21ddf-122">Shows how to retrieve text from a file one line at a time.</span></span>|  
|[<span data-ttu-id="21ddf-123">Come creare una chiave nel registro di sistema</span><span class="sxs-lookup"><span data-stu-id="21ddf-123">How to create a key in the registry</span></span>](./how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="21ddf-124">Viene mostrato come scrivere una chiave nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="21ddf-124">Shows how to write a key to the system registry.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="21ddf-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="21ddf-125">Related Sections</span></span>  
 [<span data-ttu-id="21ddf-126">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="21ddf-126">File and Stream I/O</span></span>](../../../standard/io/index.md)  
  
 [<span data-ttu-id="21ddf-127">Come copiare, eliminare e spostare file e cartelle (C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="21ddf-127">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](./how-to-copy-delete-and-move-files-and-folders.md)
  
 [<span data-ttu-id="21ddf-128">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="21ddf-128">C# Programming Guide</span></span>](../index.md)  
  
 <span data-ttu-id="21ddf-129">[Files, Folders and Drives](./index.md) (File, cartelle e unità)</span><span class="sxs-lookup"><span data-stu-id="21ddf-129">[Files, Folders and Drives](./index.md)</span></span>  
  
 <xref:System.IO?displayProperty=nameWithType>
