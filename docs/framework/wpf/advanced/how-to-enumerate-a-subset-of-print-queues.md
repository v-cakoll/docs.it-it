---
title: 'Procedura: enumerare un sottoinsieme di code di stampa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: aae41931f012f6d34fc057fdd6ee9fc9baab6e7b
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094540"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="69d89-102">Procedura: enumerare un sottoinsieme di code di stampa</span><span class="sxs-lookup"><span data-stu-id="69d89-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="69d89-103">Una situazione comune affrontata dai professionisti IT (Information Technology) che gestiscono un set di stampanti a livello aziendale consiste nel generare un elenco di stampanti con determinate caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="69d89-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="69d89-104">Questa funzionalità viene fornita dal metodo <xref:System.Printing.PrintServer.GetPrintQueues%2A> di un oggetto <xref:System.Printing.PrintServer> e dall'enumerazione <xref:System.Printing.EnumeratedPrintQueueTypes>.</span><span class="sxs-lookup"><span data-stu-id="69d89-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69d89-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="69d89-105">Example</span></span>  
 <span data-ttu-id="69d89-106">Nell'esempio seguente il codice inizia creando una matrice di flag che specificano le caratteristiche delle code di stampa che si desidera elencare.</span><span class="sxs-lookup"><span data-stu-id="69d89-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="69d89-107">In questo esempio, si stanno cercando le code di stampa installate localmente nel server di stampa e condivise.</span><span class="sxs-lookup"><span data-stu-id="69d89-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="69d89-108">L'enumerazione <xref:System.Printing.EnumeratedPrintQueueTypes> offre molte altre possibilità.</span><span class="sxs-lookup"><span data-stu-id="69d89-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="69d89-109">Il codice crea quindi un oggetto <xref:System.Printing.LocalPrintServer>, una classe derivata da <xref:System.Printing.PrintServer>.</span><span class="sxs-lookup"><span data-stu-id="69d89-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="69d89-110">Il server di stampa locale è il computer in cui è in esecuzione l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="69d89-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="69d89-111">L'ultimo passaggio significativo consiste nel passare la matrice al metodo <xref:System.Printing.PrintServer.GetPrintQueues%2A>.</span><span class="sxs-lookup"><span data-stu-id="69d89-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="69d89-112">Infine, i risultati vengono presentati all'utente.</span><span class="sxs-lookup"><span data-stu-id="69d89-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="69d89-113">Questo esempio può essere esteso con il ciclo di `foreach` che esegue l'analisi di ogni coda di stampa.</span><span class="sxs-lookup"><span data-stu-id="69d89-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="69d89-114">Ad esempio, è possibile escludere le stampanti che non supportano la stampa su due lati, facendo in modo che il ciclo chiami il metodo <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> della coda di stampa e testando il valore restituito per la presenza di duplexing.</span><span class="sxs-lookup"><span data-stu-id="69d89-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69d89-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69d89-115">See also</span></span>

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="69d89-116">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="69d89-116">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="69d89-117">Panoramica della stampa</span><span class="sxs-lookup"><span data-stu-id="69d89-117">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="69d89-118">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="69d89-118">Microsoft XPS Document Writer</span></span>](/windows/win32/printdocs/microsoft-xps-document-writer)
