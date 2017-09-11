---
title: 'Procedura: copiare, eliminare e spostare file e cartelle (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
caps.latest.revision: 13
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
ms.openlocfilehash: a4cfec46e0af0056a0de20a1ed83a370cd010055
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="4ff48-102">Procedura: copiare, eliminare e spostare file e cartelle (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="4ff48-102">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>
<span data-ttu-id="4ff48-103">Gli esempi seguenti mostrano come copiare, spostare ed eliminare file e cartelle in modo sincrono usando le classi <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName> e <xref:System.IO.DirectoryInfo?displayProperty=fullName> dello spazio dei nomi <xref:System.IO?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4ff48-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName>, and <xref:System.IO.DirectoryInfo?displayProperty=fullName> classes from the <xref:System.IO?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="4ff48-104">Questi esempi non forniscono un indicatore di stato o altri elementi di interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="4ff48-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="4ff48-105">Se si vuole fornire una finestra di dialogo di stato standard, vedere [Procedura: Fornire una finestra di dialogo dello stato per operazioni su file](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="4ff48-105">If you want to provide a standard progress dialog box, see [How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="4ff48-106">Usare <xref:System.IO.FileSystemWatcher?displayProperty=fullName> per fornire eventi che consentano di calcolare lo stato quando si opera su più file.</span><span class="sxs-lookup"><span data-stu-id="4ff48-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=fullName> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="4ff48-107">Un altro approccio consiste nell'usare pInvoke per chiamare i metodi correlati ai file pertinenti nella shell di Windows.</span><span class="sxs-lookup"><span data-stu-id="4ff48-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="4ff48-108">Per informazioni su come eseguire queste operazioni sui file in modo asincrono, vedere [I/O di file asincrono](https://msdn.microsoft.com/library/kztecsys).</span><span class="sxs-lookup"><span data-stu-id="4ff48-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](https://msdn.microsoft.com/library/kztecsys).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ff48-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ff48-109">Example</span></span>  
 <span data-ttu-id="4ff48-110">L'esempio seguente illustra come copiare file e directory.</span><span class="sxs-lookup"><span data-stu-id="4ff48-110">The following example shows how to copy files and directories.</span></span>  
  
 <span data-ttu-id="4ff48-111">[!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4ff48-111">[!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ff48-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ff48-112">Example</span></span>  
 <span data-ttu-id="4ff48-113">L'esempio seguente illustra come spostare file e directory.</span><span class="sxs-lookup"><span data-stu-id="4ff48-113">The following example shows how to move files and directories.</span></span>  
  
 <span data-ttu-id="4ff48-114">[!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4ff48-114">[!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ff48-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ff48-115">Example</span></span>  
 <span data-ttu-id="4ff48-116">L'esempio seguente illustra come eliminare file e directory.</span><span class="sxs-lookup"><span data-stu-id="4ff48-116">The following example shows how to delete files and directories.</span></span>  
  
 <span data-ttu-id="4ff48-117">[!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="4ff48-117">[!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ff48-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ff48-118">See Also</span></span>  
 <span data-ttu-id="4ff48-119"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4ff48-119"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="4ff48-120">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4ff48-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4ff48-121">[File system e Registro di sistema (Guida per programmatori C#)](index.md) </span><span class="sxs-lookup"><span data-stu-id="4ff48-121">[File System and the Registry (C# Programming Guide)](index.md) </span></span>  
 <span data-ttu-id="4ff48-122">[Procedura: Fornire una finestra di dialogo dello stato per operazioni su file](how-to-provide-a-progress-dialog-box-for-file-operations.md) </span><span class="sxs-lookup"><span data-stu-id="4ff48-122">[How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md) </span></span>  
 <span data-ttu-id="4ff48-123">[I/O di file e di flussi](https://msdn.microsoft.com/library/k3352a4t) </span><span class="sxs-lookup"><span data-stu-id="4ff48-123">[File and Stream I/O](https://msdn.microsoft.com/library/k3352a4t) </span></span>  
 [<span data-ttu-id="4ff48-124">Attività di I/O comuni</span><span class="sxs-lookup"><span data-stu-id="4ff48-124">Common I/O Tasks</span></span>](https://msdn.microsoft.com/library/ms404278)

