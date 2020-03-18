---
title: File system e il Registro di sistema - Guida per programmatori C
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: f160df456f1a3437e11de2d3660d158ae4d4bb67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75900570"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="08c30-102">File system e il Registro di sistema (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="08c30-102">File system and the registry (C# Programming Guide)</span></span>

<span data-ttu-id="08c30-103">Negli articoli seguenti viene illustrato come utilizzare C .NET per eseguire varie operazioni di base su file, cartelle e il Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="08c30-103">The following articles show how to use C# and .NET to perform various basic operations on files, folders, and the registry.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="08c30-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="08c30-104">In this section</span></span>

|<span data-ttu-id="08c30-105">**Titolo**</span><span class="sxs-lookup"><span data-stu-id="08c30-105">**Title**</span></span>|<span data-ttu-id="08c30-106">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="08c30-106">**Description**</span></span>|
|---------------|---------------------|
|[<span data-ttu-id="08c30-107">Come scorrere un albero di directory</span><span class="sxs-lookup"><span data-stu-id="08c30-107">How to iterate through a directory tree</span></span>](how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="08c30-108">Viene mostrato come scorrere manualmente una struttura ad albero di directory.</span><span class="sxs-lookup"><span data-stu-id="08c30-108">Shows how to manually iterate through a directory tree.</span></span>|
|[<span data-ttu-id="08c30-109">Come ottenere informazioni relative a file, cartelle e unità</span><span class="sxs-lookup"><span data-stu-id="08c30-109">How to get information about files, folders, and drives</span></span>](how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="08c30-110">Viene mostrato come recuperare informazioni relative a file, cartelle e unità, ad esempio la data di creazione e la dimensione.</span><span class="sxs-lookup"><span data-stu-id="08c30-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|
|[<span data-ttu-id="08c30-111">Come creare un file o una cartella</span><span class="sxs-lookup"><span data-stu-id="08c30-111">How to create a file or folder</span></span>](how-to-create-a-file-or-folder.md)|<span data-ttu-id="08c30-112">Viene mostrato come creare un nuovo file o una nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="08c30-112">Shows how to create a new file or folder.</span></span>|
|[<span data-ttu-id="08c30-113">Come copiare, eliminare e spostare file e cartelle (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="08c30-113">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="08c30-114">Viene mostrato come copiare, eliminare e spostare file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="08c30-114">Shows how to copy, delete and move files and folders.</span></span>|
|[<span data-ttu-id="08c30-115">Come fornire una finestra di dialogo dello stato di avanzamento per operazioni su file</span><span class="sxs-lookup"><span data-stu-id="08c30-115">How to provide a progress dialog box for file operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="08c30-116">Viene mostrato come visualizzare una finestra di stato Windows standard per determinate operazioni sui file.</span><span class="sxs-lookup"><span data-stu-id="08c30-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|
|[<span data-ttu-id="08c30-117">Come scrivere in un file di testo</span><span class="sxs-lookup"><span data-stu-id="08c30-117">How to write to a text file</span></span>](how-to-write-to-a-text-file.md)|<span data-ttu-id="08c30-118">Viene mostrato come scrivere in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="08c30-118">Shows how to write to a text file.</span></span>|
|[<span data-ttu-id="08c30-119">Come leggere da un file di testo</span><span class="sxs-lookup"><span data-stu-id="08c30-119">How to read from a text file</span></span>](how-to-read-from-a-text-file.md)|<span data-ttu-id="08c30-120">Viene mostrato come leggere da un file di testo.</span><span class="sxs-lookup"><span data-stu-id="08c30-120">Shows how to read from a text file.</span></span>|
|[<span data-ttu-id="08c30-121">Come leggere un file di testo una riga alla volta</span><span class="sxs-lookup"><span data-stu-id="08c30-121">How to read a text file one line at a time</span></span>](how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="08c30-122">Viene mostrato come recuperare testo da un file una riga alla volta.</span><span class="sxs-lookup"><span data-stu-id="08c30-122">Shows how to retrieve text from a file one line at a time.</span></span>|
|[<span data-ttu-id="08c30-123">Come creare una chiave nel Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="08c30-123">How to create a key in the registry</span></span>](how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="08c30-124">Viene mostrato come scrivere una chiave nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="08c30-124">Shows how to write a key to the system registry.</span></span>|

## <a name="related-sections"></a><span data-ttu-id="08c30-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="08c30-125">Related sections</span></span>

- [<span data-ttu-id="08c30-126">I/O su file e flusso</span><span class="sxs-lookup"><span data-stu-id="08c30-126">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="08c30-127">Come copiare, eliminare e spostare file e cartelle (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="08c30-127">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](how-to-copy-delete-and-move-files-and-folders.md)
- [<span data-ttu-id="08c30-128">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="08c30-128">C# Programming Guide</span></span>](../index.md)
- <xref:System.IO?displayProperty=nameWithType>
