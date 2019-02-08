---
title: 'Procedura: Aprire un file di log e accodare informazioni'
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET Framework], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 921b13e057929d7d6b283b26014a4c1f195f39c9
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674841"
---
# <a name="how-to-open-and-append-to-a-log-file"></a><span data-ttu-id="90933-102">Procedura: Aprire un file di log e accodare informazioni</span><span class="sxs-lookup"><span data-stu-id="90933-102">How to: Open and append to a log file</span></span>
<span data-ttu-id="90933-103"><xref:System.IO.StreamWriter> e <xref:System.IO.StreamReader> scrivono e leggono i caratteri nei flussi.</span><span class="sxs-lookup"><span data-stu-id="90933-103"><xref:System.IO.StreamWriter> and <xref:System.IO.StreamReader> write characters to and read characters from streams.</span></span> <span data-ttu-id="90933-104">L'esempio di codice seguente apre il file *log.txt* per l'input oppure crea il file, se non esiste già, e aggiunge informazioni alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="90933-104">The following code example opens the *log.txt* file for input, or creates it if it doesn't exist, and appends log information to the end of the file.</span></span> <span data-ttu-id="90933-105">Nell'esempio, il contenuto del file viene quindi scritto nell'output standard per la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="90933-105">The example then writes the contents of the file to standard output for display.</span></span> 

<span data-ttu-id="90933-106">In alternativa a questo esempio, è possibile archiviare le informazioni come un'unica stringa o matrice di stringhe e usare il metodo <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType> o <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType> per ottenere la stessa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="90933-106">As an alternative to this example, you could store the information as a single string or string array, and use the <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType> or <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType> method to achieve the same functionality.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90933-107">Gli utenti di Visual Basic possono scegliere di usare i metodi e le proprietà forniti dalla classe <xref:Microsoft.VisualBasic.Logging.Log> o dalla classe <xref:Microsoft.VisualBasic.FileIO.FileSystem> per creare file di log o scrivere al loro interno.</span><span class="sxs-lookup"><span data-stu-id="90933-107">Visual Basic users may choose to use the methods and properties provided by the <xref:Microsoft.VisualBasic.Logging.Log> class or <xref:Microsoft.VisualBasic.FileIO.FileSystem> class for creating or writing to log files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90933-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="90933-108">Example</span></span>  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="90933-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90933-109">See also</span></span>

- <xref:System.IO.StreamWriter>  
- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="90933-110">Procedura: Enumerare directory e file</span><span class="sxs-lookup"><span data-stu-id="90933-110">How to: Enumerate directories and files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="90933-111">Procedura: Leggere e scrivere in un file di dati appena creato</span><span class="sxs-lookup"><span data-stu-id="90933-111">How to: Read and write to a newly created data file</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="90933-112">Procedura: Leggere testo da un file</span><span class="sxs-lookup"><span data-stu-id="90933-112">How to: Read text from a file</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="90933-113">Procedura: Scrivere testo in un file</span><span class="sxs-lookup"><span data-stu-id="90933-113">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="90933-114">Procedura: Leggere caratteri da una stringa</span><span class="sxs-lookup"><span data-stu-id="90933-114">How to: Read characters from a string</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="90933-115">Procedura: Scrivere caratteri in una stringa</span><span class="sxs-lookup"><span data-stu-id="90933-115">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="90933-116">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="90933-116">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
