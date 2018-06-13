---
title: 'Procedura: leggere un file di testo una riga alla volta (Visual C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
ms.openlocfilehash: 2ed0069f9313955edc2cc46ecfd395a5f1ac2852
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339735"
---
# <a name="how-to-read-a-text-file-one-line-at-a-time-visual-c"></a><span data-ttu-id="3379e-102">Procedura: leggere un file di testo una riga alla volta (Visual C#)</span><span class="sxs-lookup"><span data-stu-id="3379e-102">How to: Read a Text File One Line at a Time (Visual C#)</span></span>
<span data-ttu-id="3379e-103">Questo esempio legge il contenuto di un file di testo, una riga alla volta, in una stringa usando il metodo `ReadLine` della classe `StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="3379e-103">This example reads the contents of a text file, one line at a time, into a string using the `ReadLine` method of the `StreamReader` class.</span></span> <span data-ttu-id="3379e-104">Ogni riga di testo è memorizzata nella stringa `line` e visualizzata nella schermata.</span><span class="sxs-lookup"><span data-stu-id="3379e-104">Each text line is stored into the string `line` and displayed on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3379e-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="3379e-105">Example</span></span>  
  
```  
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =   
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine (line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3379e-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3379e-106">Compiling the Code</span></span>  
 <span data-ttu-id="3379e-107">Copiare il codice e incollarlo nel metodo `Main` di un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="3379e-107">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
 <span data-ttu-id="3379e-108">Sostituire `"c:\test.txt"` con il nome effettivo del file.</span><span class="sxs-lookup"><span data-stu-id="3379e-108">Replace `"c:\test.txt"` with the actual file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3379e-109">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="3379e-109">Robust Programming</span></span>  
 <span data-ttu-id="3379e-110">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="3379e-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="3379e-111">È possibile che il file non esista.</span><span class="sxs-lookup"><span data-stu-id="3379e-111">The file may not exist.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="3379e-112">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3379e-112">.NET Framework Security</span></span>  
 <span data-ttu-id="3379e-113">Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="3379e-113">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="3379e-114">Ad esempio, il file `myFile.cs` potrebbe non essere un file di origine C#.</span><span class="sxs-lookup"><span data-stu-id="3379e-114">For example, the file `myFile.cs` may not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3379e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3379e-115">See Also</span></span>  
 <xref:System.IO?displayProperty=nameWithType>  
 [<span data-ttu-id="3379e-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3379e-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3379e-117">File system e Registro di sistema (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="3379e-117">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
