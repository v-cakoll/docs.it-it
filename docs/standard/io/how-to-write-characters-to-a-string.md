---
title: 'Procedura: scrivere caratteri in una stringa'
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET Framework], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
ms.openlocfilehash: 04fc21c452258a88292a886d952353ac55573121
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288251"
---
# <a name="how-to-write-characters-to-a-string"></a><span data-ttu-id="ffbb7-102">Procedura: scrivere caratteri in una stringa</span><span class="sxs-lookup"><span data-stu-id="ffbb7-102">How to: Write characters to a string</span></span>
<span data-ttu-id="ffbb7-103">Gli esempi di codice seguenti illustrano come scrivere i caratteri in modo sincrono o asincrono da una matrice di caratteri in una stringa.</span><span class="sxs-lookup"><span data-stu-id="ffbb7-103">The following code examples write characters synchronously or asynchronously from a character array into a string.</span></span>  
  
## <a name="example-write-characters-synchronously-in-a-console-app"></a><span data-ttu-id="ffbb7-104">Esempio: scrivere i caratteri in modo sincrono in un'app console</span><span class="sxs-lookup"><span data-stu-id="ffbb7-104">Example: Write characters synchronously in a console app</span></span>  
 <span data-ttu-id="ffbb7-105">L'esempio seguente usa <xref:System.IO.StringWriter> per scrivere cinque caratteri in modo sincrono in un oggetto <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="ffbb7-105">The following example uses a <xref:System.IO.StringWriter> to write five characters synchronously to a <xref:System.Text.StringBuilder> object.</span></span>
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example-write-characters-asynchronously-in-a-wpf-app"></a><span data-ttu-id="ffbb7-106">Esempio: scrivere caratteri in modo asincrono in un'app WPF</span><span class="sxs-lookup"><span data-stu-id="ffbb7-106">Example: Write characters asynchronously in a WPF app</span></span>
 <span data-ttu-id="ffbb7-107">L'esempio successivo è il code-behind di un'app WPF.</span><span class="sxs-lookup"><span data-stu-id="ffbb7-107">The next example is the code behind a WPF app.</span></span> <span data-ttu-id="ffbb7-108">Al caricamento della finestra, l'esempio legge in modo asincrono tutti i caratteri da un controllo <xref:System.Windows.Controls.TextBox> e li archivia in una matrice.</span><span class="sxs-lookup"><span data-stu-id="ffbb7-108">On window load, the example asynchronously reads all characters from a <xref:System.Windows.Controls.TextBox> control and stores them in an array.</span></span> <span data-ttu-id="ffbb7-109">Scrive quindi in modo asincrono ogni lettera o spazio su una riga separata di un controllo <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="ffbb7-109">It then asynchronously writes each letter or white-space character to a separate line of a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[StreamReaderWriter](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[StreamReaderWriter](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ffbb7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffbb7-110">See also</span></span>

- <xref:System.IO.StringWriter>  
- <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
- <xref:System.Text.StringBuilder>  
- [<span data-ttu-id="ffbb7-111">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="ffbb7-111">File and stream I/O</span></span>](index.md)  
- [<span data-ttu-id="ffbb7-112">I/O di file asincrono</span><span class="sxs-lookup"><span data-stu-id="ffbb7-112">Asynchronous file I/O</span></span>](asynchronous-file-i-o.md)  
- [<span data-ttu-id="ffbb7-113">Procedura: enumerare directory e file</span><span class="sxs-lookup"><span data-stu-id="ffbb7-113">How to: Enumerate directories and files</span></span>](how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="ffbb7-114">Procedura: leggere e scrivere in un file di dati appena creato</span><span class="sxs-lookup"><span data-stu-id="ffbb7-114">How to: Read and write to a newly created data file</span></span>](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="ffbb7-115">Procedura: aprire e accodare un file di log</span><span class="sxs-lookup"><span data-stu-id="ffbb7-115">How to: Open and append to a log file</span></span>](how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="ffbb7-116">Procedura: leggere testo da un file</span><span class="sxs-lookup"><span data-stu-id="ffbb7-116">How to: Read text from a file</span></span>](how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="ffbb7-117">Procedura: scrivere testo in un file</span><span class="sxs-lookup"><span data-stu-id="ffbb7-117">How to: Write text to a file</span></span>](how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="ffbb7-118">Procedura: leggere caratteri da una stringa</span><span class="sxs-lookup"><span data-stu-id="ffbb7-118">How to: Read characters from a string</span></span>](how-to-read-characters-from-a-string.md)
