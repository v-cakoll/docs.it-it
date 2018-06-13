---
title: 'Procedura: copiare, eliminare e spostare file e cartelle (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 5debb2cbfa5ada45447e280169b9fe66d1a15a53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330080"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="63aae-102">Procedura: copiare, eliminare e spostare file e cartelle (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="63aae-102">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>
<span data-ttu-id="63aae-103">Gli esempi seguenti mostrano come copiare, spostare ed eliminare file e cartelle in modo sincrono usando le classi <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType> e <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> dello spazio dei nomi <xref:System.IO?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="63aae-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="63aae-104">Questi esempi non forniscono un indicatore di stato o altri elementi di interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="63aae-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="63aae-105">Se si vuole fornire una finestra di dialogo di stato standard, vedere [Procedura: Fornire una finestra di dialogo dello stato per operazioni su file](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="63aae-105">If you want to provide a standard progress dialog box, see [How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="63aae-106">Usare <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> per fornire eventi che consentano di calcolare lo stato quando si opera su più file.</span><span class="sxs-lookup"><span data-stu-id="63aae-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="63aae-107">Un altro approccio consiste nell'usare pInvoke per chiamare i metodi correlati ai file pertinenti nella shell di Windows.</span><span class="sxs-lookup"><span data-stu-id="63aae-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="63aae-108">Per informazioni su come eseguire queste operazioni sui file in modo asincrono, vedere [I/O di file asincrono](https://msdn.microsoft.com/library/kztecsys).</span><span class="sxs-lookup"><span data-stu-id="63aae-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](https://msdn.microsoft.com/library/kztecsys).</span></span>  
  
## <a name="example"></a><span data-ttu-id="63aae-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="63aae-109">Example</span></span>  
 <span data-ttu-id="63aae-110">L'esempio seguente illustra come copiare file e directory.</span><span class="sxs-lookup"><span data-stu-id="63aae-110">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="63aae-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="63aae-111">Example</span></span>  
 <span data-ttu-id="63aae-112">L'esempio seguente illustra come spostare file e directory.</span><span class="sxs-lookup"><span data-stu-id="63aae-112">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="63aae-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="63aae-113">Example</span></span>  
 <span data-ttu-id="63aae-114">L'esempio seguente illustra come eliminare file e directory.</span><span class="sxs-lookup"><span data-stu-id="63aae-114">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="63aae-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63aae-115">See Also</span></span>  
 <xref:System.IO?displayProperty=nameWithType>  
 [<span data-ttu-id="63aae-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="63aae-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="63aae-117">File system e Registro di sistema (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="63aae-117">File System and the Registry (C# Programming Guide)</span></span>](index.md)  
 [<span data-ttu-id="63aae-118">Procedura: Creare una finestra di dialogo dello stato di avanzamento per operazioni su file</span><span class="sxs-lookup"><span data-stu-id="63aae-118">How to: Provide a Progress Dialog Box for File Operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)  
 [<span data-ttu-id="63aae-119">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="63aae-119">File and Stream I/O</span></span>](https://msdn.microsoft.com/library/k3352a4t)  
 [<span data-ttu-id="63aae-120">Attività di I/O comuni</span><span class="sxs-lookup"><span data-stu-id="63aae-120">Common I/O Tasks</span></span>](https://msdn.microsoft.com/library/ms404278)
