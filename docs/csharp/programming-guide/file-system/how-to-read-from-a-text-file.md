---
title: 'Procedura: leggere da un file di testo (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2af6102ac6793b4612a6fbc41f8c50189cc24d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="db046-102">Procedura: leggere da un file di testo (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="db046-102">How to: Read From a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="db046-103">Questo esempio legge il contenuto di un file di testo usando i metodi statici <xref:System.IO.File.ReadAllText%2A> e <xref:System.IO.File.ReadAllLines%2A> della classe <xref:System.IO.File?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="db046-103">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=nameWithType> class.</span></span>  
  
 <span data-ttu-id="db046-104">Per un esempio che usa <xref:System.IO.StreamReader>, vedere [Procedura: leggere un file di testo una riga alla volta](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span><span class="sxs-lookup"><span data-stu-id="db046-104">For an example that uses <xref:System.IO.StreamReader>, see [How to: Read a Text File One Line at a Time](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db046-105">I file che vengono usati in questo esempio sono creati nell'argomento [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md) (Procedura: scrivere un file di testo).</span><span class="sxs-lookup"><span data-stu-id="db046-105">The files that are used in this example are created in the topic [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="db046-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="db046-106">Example</span></span>  
 [!code-csharp[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="db046-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="db046-107">Compiling the Code</span></span>  
 <span data-ttu-id="db046-108">Copiare il codice e incollarlo in un'applicazione console C#.</span><span class="sxs-lookup"><span data-stu-id="db046-108">Copy the code and paste it into a C# console application.</span></span>  
  
 <span data-ttu-id="db046-109">Se non si usano i file di testo da [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md) (Procedura: scrivere un file di testo), sostituire l'argomento `ReadAllText` e `ReadAllLines` con il nome file e il percorso appropriati nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="db046-109">If you are not using the text files from [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="db046-110">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="db046-110">Robust Programming</span></span>  
 <span data-ttu-id="db046-111">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="db046-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="db046-112">Il file non esiste o non esiste nella posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="db046-112">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="db046-113">Controllare il percorso e la digitazione del nome file.</span><span class="sxs-lookup"><span data-stu-id="db046-113">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="db046-114">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="db046-114">.NET Framework Security</span></span>  
 <span data-ttu-id="db046-115">Non basarsi sul nome di un file per determinare il contenuto del file.</span><span class="sxs-lookup"><span data-stu-id="db046-115">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="db046-116">Ad esempio, il file `myFile.cs` potrebbe non essere un file di origine C#.</span><span class="sxs-lookup"><span data-stu-id="db046-116">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db046-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db046-117">See Also</span></span>  
 <xref:System.IO?displayProperty=nameWithType>  
 [<span data-ttu-id="db046-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="db046-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="db046-119">File system e Registro di sistema (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="db046-119">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
