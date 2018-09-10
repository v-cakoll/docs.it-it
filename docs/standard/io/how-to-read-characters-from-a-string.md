---
title: 'Procedura: Leggere caratteri da una stringa'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 13a57f8ea7db91e5357ecfb20c4e907f2706f78d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44194968"
---
# <a name="how-to-read-characters-from-a-string"></a><span data-ttu-id="85594-102">Procedura: Leggere caratteri da una stringa</span><span class="sxs-lookup"><span data-stu-id="85594-102">How to: Read Characters from a String</span></span>
<span data-ttu-id="85594-103">Gli esempi di codice seguenti illustrano come leggere i caratteri in modo sincrono e asincrono da una stringa.</span><span class="sxs-lookup"><span data-stu-id="85594-103">The following code examples show how to read characters synchronously and asynchronously from a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85594-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="85594-104">Example</span></span>  
 <span data-ttu-id="85594-105">Questo esempio legge 13 caratteri in modo sincrono da una stringa, li archivia in una matrice e li visualizza.</span><span class="sxs-lookup"><span data-stu-id="85594-105">This example reads 13 characters synchronously from a string, stores them in an array, and displays those characters.</span></span> <span data-ttu-id="85594-106">Legge quindi i caratteri rimanenti nella stringa, li archivia nella matrice a partire dal sesto elemento e visualizza il contenuto della matrice.</span><span class="sxs-lookup"><span data-stu-id="85594-106">It then reads the remaining characters in the string, stores them in the array starting at the sixth element, and displays the contents of the array.</span></span>  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="85594-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="85594-107">Example</span></span>  
 <span data-ttu-id="85594-108">L'esempio seguente legge tutti i caratteri in modo asincrono da un controllo <xref:System.Windows.Controls.TextBox> e li archivia in una matrice.</span><span class="sxs-lookup"><span data-stu-id="85594-108">The next example reads all the characters asynchronously from a <xref:System.Windows.Controls.TextBox> control, and stores them in an array.</span></span> <span data-ttu-id="85594-109">Scrive quindi in modo asincrono ogni lettera o spazio su una riga separata seguita da un'interruzione di riga in un controllo <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="85594-109">It then asynchronously writes each letter or white space character on a separate line followed by a line break to a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="85594-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85594-110">See also</span></span>

- <xref:System.IO.StringReader>  
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="85594-111">I/O di file asincrono</span><span class="sxs-lookup"><span data-stu-id="85594-111">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [<span data-ttu-id="85594-112">Procedura: creare una visualizzazione directory</span><span class="sxs-lookup"><span data-stu-id="85594-112">NIB: How to: Create a Directory Listing</span></span>](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
- [<span data-ttu-id="85594-113">Procedura: Leggere e scrivere su un file di dati appena creato</span><span class="sxs-lookup"><span data-stu-id="85594-113">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="85594-114">Procedura: Aprire e accodare un file di log</span><span class="sxs-lookup"><span data-stu-id="85594-114">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="85594-115">Procedura: Leggere testo da un file</span><span class="sxs-lookup"><span data-stu-id="85594-115">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="85594-116">Procedura: Scrivere un testo in un file</span><span class="sxs-lookup"><span data-stu-id="85594-116">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="85594-117">Procedura: Scrivere caratteri in una stringa</span><span class="sxs-lookup"><span data-stu-id="85594-117">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="85594-118">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="85594-118">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
