---
title: 'Procedura: leggere e scrivere in un file di dati appena creato'
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET Framework], reading data
- I/O [.NET Framework], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
ms.openlocfilehash: 3772aeeb25d1251a13fde2a0e51a913e5e39eabc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155750"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a><span data-ttu-id="2cd05-102">Procedura: leggere e scrivere in un file di dati appena creato</span><span class="sxs-lookup"><span data-stu-id="2cd05-102">How to: Read and write to a newly created data file</span></span>
<span data-ttu-id="2cd05-103">Le classi <xref:System.IO.BinaryWriter?displayProperty=nameWithType> e <xref:System.IO.BinaryReader?displayProperty=nameWithType> vengono usate per scrivere e leggere i dati diversi da stringhe di caratteri.</span><span class="sxs-lookup"><span data-stu-id="2cd05-103">The <xref:System.IO.BinaryWriter?displayProperty=nameWithType> and <xref:System.IO.BinaryReader?displayProperty=nameWithType> classes are used for writing and reading data other than character strings.</span></span> <span data-ttu-id="2cd05-104">L'esempio seguente illustra come creare un flusso di file vuoto, quindi scrivere e leggere dati in tale flusso.</span><span class="sxs-lookup"><span data-stu-id="2cd05-104">The following example shows how to create an empty file stream, write data to it, and read data from it.</span></span>

<span data-ttu-id="2cd05-105">L'esempio crea un file di dati denominato *Test.data* nella directory corrente, crea gli oggetti <xref:System.IO.BinaryWriter> e <xref:System.IO.BinaryReader> associati e usa l'oggetto <xref:System.IO.BinaryWriter> per scrivere i valori interi da 0 a 10 in *Test.data*, lasciando il puntatore del file alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="2cd05-105">The example creates a data file called *Test.data* in the current directory, creates the associated <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader> objects, and uses the <xref:System.IO.BinaryWriter> object to write the integers 0 through 10 to *Test.data*, which leaves the file pointer at the end of the file.</span></span> <span data-ttu-id="2cd05-106">L'oggetto <xref:System.IO.BinaryReader> reimposta quindi il puntatore del file sull'origine e legge il contenuto specificato.</span><span class="sxs-lookup"><span data-stu-id="2cd05-106">The <xref:System.IO.BinaryReader> object then sets the file pointer back to the origin and reads out the specified content.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2cd05-107">Se *Test.data* è già presente nella directory corrente, viene generata un'eccezione <xref:System.IO.IOException>.</span><span class="sxs-lookup"><span data-stu-id="2cd05-107">If *Test.data* already exists in the current directory, an <xref:System.IO.IOException> exception is thrown.</span></span> <span data-ttu-id="2cd05-108">Usare l'opzione della modalità file <xref:System.IO.FileMode.Create?displayProperty=nameWithType> invece di <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType> per creare sempre un nuovo file senza generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2cd05-108">Use the file mode option <xref:System.IO.FileMode.Create?displayProperty=nameWithType> rather than <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType> to always create a new file without throwing an exception.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cd05-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="2cd05-109">Example</span></span>  
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="2cd05-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cd05-110">See also</span></span>

- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryWriter>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
- <xref:System.IO.SeekOrigin>  
- [<span data-ttu-id="2cd05-111">Procedura: enumerare directory e file</span><span class="sxs-lookup"><span data-stu-id="2cd05-111">How to: Enumerate directories and files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="2cd05-112">Procedura: aprire e accodare un file di log</span><span class="sxs-lookup"><span data-stu-id="2cd05-112">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="2cd05-113">Procedura: leggere testo da un file</span><span class="sxs-lookup"><span data-stu-id="2cd05-113">How to: Read text from a file</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="2cd05-114">Procedura: scrivere testo in un file</span><span class="sxs-lookup"><span data-stu-id="2cd05-114">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="2cd05-115">Procedura: leggere caratteri da una stringa</span><span class="sxs-lookup"><span data-stu-id="2cd05-115">How to: Read characters from a string</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="2cd05-116">Procedura: scrivere caratteri in una stringa</span><span class="sxs-lookup"><span data-stu-id="2cd05-116">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="2cd05-117">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="2cd05-117">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
