---
title: 'Procedura: Enumerare un sottoinsieme di code di stampa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: adcfff0196bd0430ec1ae563fbd5489062de11f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776064"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="d0386-102">Procedura: Enumerare un sottoinsieme di code di stampa</span><span class="sxs-lookup"><span data-stu-id="d0386-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="d0386-103">Una situazione comune affrontata dai professionisti informatici (IT) gestisce un set a livello aziendale delle stampanti consiste nel generare un elenco delle stampanti con determinate caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="d0386-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="d0386-104">Questa funzionalità viene fornita per il <xref:System.Printing.PrintServer.GetPrintQueues%2A> metodo di un <xref:System.Printing.PrintServer> oggetto e il <xref:System.Printing.EnumeratedPrintQueueTypes> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="d0386-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0386-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0386-105">Example</span></span>  
 <span data-ttu-id="d0386-106">Nell'esempio seguente, il codice inizia creando una matrice di flag che specificano le caratteristiche delle code di stampa che si desidera elencare.</span><span class="sxs-lookup"><span data-stu-id="d0386-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="d0386-107">In questo esempio, si ricercano le code di stampa che vengono installate localmente nei server di stampa e sono condivisi.</span><span class="sxs-lookup"><span data-stu-id="d0386-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="d0386-108">Il <xref:System.Printing.EnumeratedPrintQueueTypes> enumerazione fornisce molte altre possibilità.</span><span class="sxs-lookup"><span data-stu-id="d0386-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="d0386-109">Il codice crea quindi una <xref:System.Printing.LocalPrintServer> dell'oggetto, una classe derivata da <xref:System.Printing.PrintServer>.</span><span class="sxs-lookup"><span data-stu-id="d0386-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="d0386-110">Il server di stampa locale è il computer in cui viene eseguita l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d0386-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="d0386-111">L'ultimo passaggio significativo consiste nel passare la matrice di <xref:System.Printing.PrintServer.GetPrintQueues%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="d0386-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="d0386-112">Infine, i risultati vengono presentati all'utente.</span><span class="sxs-lookup"><span data-stu-id="d0386-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="d0386-113">È possibile estendere questo esempio facendo in modo che il `foreach` ciclo che eseguire ulteriori passaggi attraverso ogni coda di stampa screening.</span><span class="sxs-lookup"><span data-stu-id="d0386-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="d0386-114">Ad esempio, è possibile escludere le stampanti che non supportano la stampa fronte retro facendo in modo che la chiamata di ciclo ogni coda di stampa <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> metodo ed eseguire test del valore restituito per la presenza di stampa fronte retro.</span><span class="sxs-lookup"><span data-stu-id="d0386-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0386-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0386-115">See also</span></span>

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="d0386-116">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="d0386-116">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="d0386-117">Panoramica della stampa</span><span class="sxs-lookup"><span data-stu-id="d0386-117">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="d0386-118">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="d0386-118">Microsoft XPS Document Writer</span></span>](https://go.microsoft.com/fwlink/?LinkId=147319)
