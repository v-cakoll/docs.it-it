---
title: 'Procedura: aprire e accodare un file di log'
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
ms.openlocfilehash: 025c35344b9262e1f2fa6da87b68e46e21a54222
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291825"
---
# <a name="how-to-open-and-append-to-a-log-file"></a><span data-ttu-id="7b76d-102">Procedura: aprire e accodare un file di log</span><span class="sxs-lookup"><span data-stu-id="7b76d-102">How to: Open and append to a log file</span></span>
<span data-ttu-id="7b76d-103"><xref:System.IO.StreamWriter> e <xref:System.IO.StreamReader> scrivono e leggono i caratteri nei flussi.</span><span class="sxs-lookup"><span data-stu-id="7b76d-103"><xref:System.IO.StreamWriter> and <xref:System.IO.StreamReader> write characters to and read characters from streams.</span></span> <span data-ttu-id="7b76d-104">L'esempio di codice seguente apre il file *log.txt* per l'input oppure crea il file, se non esiste già, e aggiunge informazioni alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="7b76d-104">The following code example opens the *log.txt* file for input, or creates it if it doesn't exist, and appends log information to the end of the file.</span></span> <span data-ttu-id="7b76d-105">Nell'esempio, il contenuto del file viene quindi scritto nell'output standard per la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7b76d-105">The example then writes the contents of the file to standard output for display.</span></span>

<span data-ttu-id="7b76d-106">In alternativa a questo esempio, è possibile archiviare le informazioni come un'unica stringa o matrice di stringhe e usare il metodo <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType> o <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType> per ottenere la stessa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7b76d-106">As an alternative to this example, you could store the information as a single string or string array, and use the <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType> or <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType> method to achieve the same functionality.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b76d-107">Gli utenti di Visual Basic possono scegliere di usare i metodi e le proprietà forniti dalla classe <xref:Microsoft.VisualBasic.Logging.Log> o dalla classe <xref:Microsoft.VisualBasic.FileIO.FileSystem> per creare file di log o scrivere al loro interno.</span><span class="sxs-lookup"><span data-stu-id="7b76d-107">Visual Basic users may choose to use the methods and properties provided by the <xref:Microsoft.VisualBasic.Logging.Log> class or <xref:Microsoft.VisualBasic.FileIO.FileSystem> class for creating or writing to log files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b76d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="7b76d-108">Example</span></span>  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7b76d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b76d-109">See also</span></span>

- <xref:System.IO.StreamWriter>  
- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="7b76d-110">Procedura: enumerare directory e file</span><span class="sxs-lookup"><span data-stu-id="7b76d-110">How to: Enumerate directories and files</span></span>](how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="7b76d-111">Procedura: leggere e scrivere in un file di dati appena creato</span><span class="sxs-lookup"><span data-stu-id="7b76d-111">How to: Read and write to a newly created data file</span></span>](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="7b76d-112">Procedura: leggere testo da un file</span><span class="sxs-lookup"><span data-stu-id="7b76d-112">How to: Read text from a file</span></span>](how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="7b76d-113">Procedura: scrivere testo in un file</span><span class="sxs-lookup"><span data-stu-id="7b76d-113">How to: Write text to a file</span></span>](how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="7b76d-114">Procedura: leggere caratteri da una stringa</span><span class="sxs-lookup"><span data-stu-id="7b76d-114">How to: Read characters from a string</span></span>](how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="7b76d-115">Procedura: scrivere caratteri in una stringa</span><span class="sxs-lookup"><span data-stu-id="7b76d-115">How to: Write characters to a string</span></span>](how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="7b76d-116">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="7b76d-116">File and stream I/O</span></span>](index.md)
