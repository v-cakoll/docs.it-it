---
title: "Procedura: ottenere informazioni relative a file, cartelle e unità (Guida per programmatori C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
caps.latest.revision: 30
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
ms.openlocfilehash: 6067ea9d51c31c9398c7b1fcd83ca8fa3a4fec76
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a><span data-ttu-id="92a19-102">Procedura: ottenere informazioni relative a file, cartelle e unità (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="92a19-102">How to: Get Information About Files, Folders, and Drives  (C# Programming Guide)</span></span>
<span data-ttu-id="92a19-103">In .NET Framework è possibile accedere a informazioni sul file system mediante le classi seguenti:</span><span class="sxs-lookup"><span data-stu-id="92a19-103">In the .NET Framework, you can access file system information by using the following classes:</span></span>  
  
-   <xref:System.IO.FileInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DirectoryInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DriveInfo?displayProperty=fullName>  
  
-   <xref:System.IO.Directory?displayProperty=fullName>  
  
-   <xref:System.IO.File?displayProperty=fullName>  
  
 <span data-ttu-id="92a19-104">Le classi <xref:System.IO.FileInfo> e <xref:System.IO.DirectoryInfo> rappresentano un file o una directory e contengono proprietà che espongono molti degli attributi di file supportati dal file system NTFS.</span><span class="sxs-lookup"><span data-stu-id="92a19-104">The <xref:System.IO.FileInfo> and <xref:System.IO.DirectoryInfo> classes represent a file or directory and contain properties that expose many of the file attributes that are supported by the NTFS file system.</span></span> <span data-ttu-id="92a19-105">Contengono anche i metodi per l'apertura, la chiusura, lo spostamento e l'eliminazione di file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="92a19-105">They also contain methods for opening, closing, moving, and deleting files and folders.</span></span> <span data-ttu-id="92a19-106">È possibile creare istanze di queste classi passando al costruttore una stringa che rappresenta il nome del file, della cartella o dell'unità:</span><span class="sxs-lookup"><span data-stu-id="92a19-106">You can create instances of these classes by passing a string that represents the name of the file, folder, or drive in to the constructor:</span></span>  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 <span data-ttu-id="92a19-107">È anche possibile ottenere i nomi di file, cartelle o unità tramite chiamate a <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=fullName>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=fullName> e <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="92a19-107">You can also obtain the names of files, folders, or drives by using calls to <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=fullName>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=fullName>, and <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="92a19-108">Le classi <xref:System.IO.Directory?displayProperty=fullName> e <xref:System.IO.File?displayProperty=fullName> forniscono metodi statici per il recupero di informazioni su file e directory.</span><span class="sxs-lookup"><span data-stu-id="92a19-108">The <xref:System.IO.Directory?displayProperty=fullName> and <xref:System.IO.File?displayProperty=fullName> classes provide static methods for retrieving information about directories and files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92a19-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="92a19-109">Example</span></span>  
 <span data-ttu-id="92a19-110">L'esempio seguente illustra vari modi per accedere alle informazioni su file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="92a19-110">The following example shows various ways to access information about files and folders.</span></span>  
  
 <span data-ttu-id="92a19-111">[!code-cs[csFilesandFolders#6](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-get-information-about-files-folders-and-drives_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="92a19-111">[!code-cs[csFilesandFolders#6](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-get-information-about-files-folders-and-drives_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="92a19-112">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="92a19-112">Robust Programming</span></span>  
 <span data-ttu-id="92a19-113">Quando si elaborano stringhe di percorso specificate dall'utente, occorre gestire anche le eccezioni per le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="92a19-113">When you process user-specified path strings, you should also handle exceptions for the following conditions:</span></span>  
  
-   <span data-ttu-id="92a19-114">Il nome file non è valido.</span><span class="sxs-lookup"><span data-stu-id="92a19-114">The file name is malformed.</span></span> <span data-ttu-id="92a19-115">Ad esempio, contiene caratteri non validi o solo spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="92a19-115">For example, it contains invalid characters or only white space.</span></span>  
  
-   <span data-ttu-id="92a19-116">Il nome del file è Null.</span><span class="sxs-lookup"><span data-stu-id="92a19-116">The file name is null.</span></span>  
  
-   <span data-ttu-id="92a19-117">La lunghezza del nome del file è maggiore della lunghezza massima definita nel sistema.</span><span class="sxs-lookup"><span data-stu-id="92a19-117">The file name is longer than the system-defined maximum length.</span></span>  
  
-   <span data-ttu-id="92a19-118">Il nome del file contiene i due punti (:).</span><span class="sxs-lookup"><span data-stu-id="92a19-118">The file name contains a colon (:).</span></span>  
  
 <span data-ttu-id="92a19-119">Se l'applicazione non ha autorizzazioni sufficienti per leggere il file specificato, il metodo `Exists` restituisce `false` indipendentemente dal fatto che il percorso esista. Il metodo non genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="92a19-119">If the application does not have sufficient permissions to read the specified file, the `Exists` method returns `false` regardless of whether a path exists; the method does not throw an exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92a19-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92a19-120">See Also</span></span>  
 <span data-ttu-id="92a19-121"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="92a19-121"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="92a19-122">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="92a19-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="92a19-123">File system e Registro di sistema (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="92a19-123">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)

