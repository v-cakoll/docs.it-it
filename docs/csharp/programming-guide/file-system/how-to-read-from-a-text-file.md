---
title: Come leggere da un file di testo-guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: 8f79d22a86390ca931b05262e50865d852c154c7
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241747"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="77e46-102">Come leggere da un file di testo (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="77e46-102">How to read from a text file (C# Programming Guide)</span></span>
<span data-ttu-id="77e46-103">Questo esempio legge il contenuto di un file di testo usando i metodi statici <xref:System.IO.File.ReadAllText%2A> e <xref:System.IO.File.ReadAllLines%2A> della classe <xref:System.IO.File?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="77e46-103">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=nameWithType> class.</span></span>  
  
<span data-ttu-id="77e46-104">Per un esempio che usa <xref:System.IO.StreamReader> , vedere [come leggere un file di testo una riga alla volta](./how-to-read-a-text-file-one-line-at-a-time.md).</span><span class="sxs-lookup"><span data-stu-id="77e46-104">For an example that uses <xref:System.IO.StreamReader>, see [How to read a text file one line at a time](./how-to-read-a-text-file-one-line-at-a-time.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="77e46-105">I file usati in questo esempio vengono creati nell'argomento [come scrivere in un file di testo](./how-to-write-to-a-text-file.md).</span><span class="sxs-lookup"><span data-stu-id="77e46-105">The files that are used in this example are created in the topic [How to write to a text file](./how-to-write-to-a-text-file.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="77e46-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="77e46-106">Example</span></span>  
 [!code-csharp[csFilesandFolders#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="77e46-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="77e46-107">Compiling the Code</span></span>  
 <span data-ttu-id="77e46-108">Copiare il codice e incollarlo in un'applicazione console C#.</span><span class="sxs-lookup"><span data-stu-id="77e46-108">Copy the code and paste it into a C# console application.</span></span>  
  
<span data-ttu-id="77e46-109">Se non si utilizzano i file di testo da [come scrivere in un file di testo](./how-to-write-to-a-text-file.md), sostituire l'argomento `ReadAllText` con e `ReadAllLines` con il percorso e il nome file appropriati nel computer.</span><span class="sxs-lookup"><span data-stu-id="77e46-109">If you are not using the text files from [How to write to a text file](./how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>
  
## <a name="robust-programming"></a><span data-ttu-id="77e46-110">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="77e46-110">Robust Programming</span></span>  
 <span data-ttu-id="77e46-111">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="77e46-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="77e46-112">Il file non esiste o non esiste nella posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="77e46-112">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="77e46-113">Controllare il percorso e la digitazione del nome file.</span><span class="sxs-lookup"><span data-stu-id="77e46-113">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="77e46-114">Sicurezza .NET</span><span class="sxs-lookup"><span data-stu-id="77e46-114">.NET Security</span></span>  
 <span data-ttu-id="77e46-115">Non basarsi sul nome di un file per determinare il contenuto del file.</span><span class="sxs-lookup"><span data-stu-id="77e46-115">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="77e46-116">Ad esempio, il file `myFile.cs` potrebbe non essere un file di origine C#.</span><span class="sxs-lookup"><span data-stu-id="77e46-116">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77e46-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77e46-117">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="77e46-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="77e46-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="77e46-119">File system e Registro di sistema (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="77e46-119">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
