---
title: 'Procedura: aprire e accodare un file di log'
description: Aprire e accodare un file di log utilizzando le classi StreamWriter e StreamReader in .NET, che scrivono e leggono i caratteri dai flussi.
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
ms.openlocfilehash: a66dadd24cc327824e91df733f11a23112cd384a
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769171"
---
# <a name="how-to-open-and-append-to-a-log-file"></a><span data-ttu-id="5f005-103">Procedura: aprire e accodare un file di log</span><span class="sxs-lookup"><span data-stu-id="5f005-103">How to: Open and append to a log file</span></span>
<span data-ttu-id="5f005-104"><xref:System.IO.StreamWriter> e <xref:System.IO.StreamReader> scrivono e leggono i caratteri nei flussi.</span><span class="sxs-lookup"><span data-stu-id="5f005-104"><xref:System.IO.StreamWriter> and <xref:System.IO.StreamReader> write characters to and read characters from streams.</span></span> <span data-ttu-id="5f005-105">L'esempio di codice seguente apre il file *log.txt* per l'input oppure crea il file, se non esiste già, e aggiunge informazioni alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="5f005-105">The following code example opens the *log.txt* file for input, or creates it if it doesn't exist, and appends log information to the end of the file.</span></span> <span data-ttu-id="5f005-106">Nell'esempio, il contenuto del file viene quindi scritto nell'output standard per la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f005-106">The example then writes the contents of the file to standard output for display.</span></span>

<span data-ttu-id="5f005-107">In alternativa a questo esempio, è possibile archiviare le informazioni come un'unica stringa o matrice di stringhe e usare il metodo <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType> o <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType> per ottenere la stessa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5f005-107">As an alternative to this example, you could store the information as a single string or string array, and use the <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType> or <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType> method to achieve the same functionality.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f005-108">Gli utenti di Visual Basic possono scegliere di usare i metodi e le proprietà forniti dalla classe <xref:Microsoft.VisualBasic.Logging.Log> o dalla classe <xref:Microsoft.VisualBasic.FileIO.FileSystem> per creare file di log o scrivere al loro interno.</span><span class="sxs-lookup"><span data-stu-id="5f005-108">Visual Basic users may choose to use the methods and properties provided by the <xref:Microsoft.VisualBasic.Logging.Log> class or <xref:Microsoft.VisualBasic.FileIO.FileSystem> class for creating or writing to log files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f005-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f005-109">Example</span></span>  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5f005-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f005-110">See also</span></span>

- <xref:System.IO.StreamWriter>  
- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="5f005-111">Procedura: enumerare directory e file</span><span class="sxs-lookup"><span data-stu-id="5f005-111">How to: Enumerate directories and files</span></span>](how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="5f005-112">Procedura: leggere e scrivere in un file di dati appena creato</span><span class="sxs-lookup"><span data-stu-id="5f005-112">How to: Read and write to a newly created data file</span></span>](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="5f005-113">Procedura: leggere testo da un file</span><span class="sxs-lookup"><span data-stu-id="5f005-113">How to: Read text from a file</span></span>](how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="5f005-114">Procedura: scrivere testo in un file</span><span class="sxs-lookup"><span data-stu-id="5f005-114">How to: Write text to a file</span></span>](how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="5f005-115">Procedura: leggere caratteri da una stringa</span><span class="sxs-lookup"><span data-stu-id="5f005-115">How to: Read characters from a string</span></span>](how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="5f005-116">Procedura: scrivere caratteri in una stringa</span><span class="sxs-lookup"><span data-stu-id="5f005-116">How to: Write characters to a string</span></span>](how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="5f005-117">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="5f005-117">File and stream I/O</span></span>](index.md)
