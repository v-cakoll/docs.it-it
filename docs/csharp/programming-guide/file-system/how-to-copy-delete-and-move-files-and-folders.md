---
title: Come copiare, eliminare e spostare file e cartelle- C# Guida alla programmazione
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 662f0ab3b9e69aa8bfb0085f42f577b850029e4d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712273"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="50902-102">Come copiare, eliminare e spostare file e cartelle (C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="50902-102">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>
<span data-ttu-id="50902-103">Gli esempi seguenti mostrano come copiare, spostare ed eliminare file e cartelle in modo sincrono usando le classi <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType> e <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> dello spazio dei nomi <xref:System.IO?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="50902-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="50902-104">Questi esempi non forniscono un indicatore di stato o altri elementi di interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="50902-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="50902-105">Se si desidera fornire una finestra di dialogo di stato standard, vedere [come fornire una finestra di dialogo di stato per le operazioni sui file](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="50902-105">If you want to provide a standard progress dialog box, see [How to provide a progress dialog box for file operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="50902-106">Usare <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> per fornire eventi che consentano di calcolare lo stato quando si opera su più file.</span><span class="sxs-lookup"><span data-stu-id="50902-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="50902-107">Un altro approccio consiste nell'usare pInvoke per chiamare i metodi correlati ai file pertinenti nella shell di Windows.</span><span class="sxs-lookup"><span data-stu-id="50902-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="50902-108">Per informazioni su come eseguire queste operazioni sui file in modo asincrono, vedere [I/O di file asincrono](../../../standard/io/asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="50902-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](../../../standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="50902-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="50902-109">Example</span></span>  
 <span data-ttu-id="50902-110">L'esempio seguente illustra come copiare file e directory.</span><span class="sxs-lookup"><span data-stu-id="50902-110">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#7)]  
  
## <a name="example"></a><span data-ttu-id="50902-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="50902-111">Example</span></span>  
 <span data-ttu-id="50902-112">L'esempio seguente illustra come spostare file e directory.</span><span class="sxs-lookup"><span data-stu-id="50902-112">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#8)]  
  
## <a name="example"></a><span data-ttu-id="50902-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="50902-113">Example</span></span>  
 <span data-ttu-id="50902-114">L'esempio seguente illustra come eliminare file e directory.</span><span class="sxs-lookup"><span data-stu-id="50902-114">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="50902-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50902-115">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="50902-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="50902-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="50902-117">File system e Registro di sistema (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="50902-117">File System and the Registry (C# Programming Guide)</span></span>](index.md)
- [<span data-ttu-id="50902-118">Come specificare una finestra di dialogo di stato per le operazioni su file</span><span class="sxs-lookup"><span data-stu-id="50902-118">How to provide a progress dialog box for file operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)
- [<span data-ttu-id="50902-119">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="50902-119">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="50902-120">Attività di I/O comuni</span><span class="sxs-lookup"><span data-stu-id="50902-120">Common I/O Tasks</span></span>](../../../standard/io/common-i-o-tasks.md)
