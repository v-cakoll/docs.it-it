---
title: 'Procedura: enumerare un sottoinsieme di code di stampa'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 393d1692526551b1eb9aa16f48d3c78c3cd6692f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="9cea5-102">Procedura: enumerare un sottoinsieme di code di stampa</span><span class="sxs-lookup"><span data-stu-id="9cea5-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="9cea5-103">Una situazione comune riscontrata da professionisti IT (IT) la gestione di un set a livello aziendale di stampanti consiste nel generare un elenco delle stampanti con determinate caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="9cea5-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="9cea5-104">Questa funzionalità viene fornita per il <xref:System.Printing.PrintServer.GetPrintQueues%2A> metodo di un <xref:System.Printing.PrintServer> oggetto e <xref:System.Printing.EnumeratedPrintQueueTypes> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9cea5-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cea5-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="9cea5-105">Example</span></span>  
 <span data-ttu-id="9cea5-106">Nell'esempio seguente, il codice inizia creando una matrice di flag che specificano le caratteristiche delle code di stampa che si desidera elencare.</span><span class="sxs-lookup"><span data-stu-id="9cea5-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="9cea5-107">In questo esempio, si sta cercando le code di stampa vengono installate localmente nel server di stampa e condivise.</span><span class="sxs-lookup"><span data-stu-id="9cea5-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="9cea5-108">Il <xref:System.Printing.EnumeratedPrintQueueTypes> enumerazione offre molte altre possibilità.</span><span class="sxs-lookup"><span data-stu-id="9cea5-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="9cea5-109">Il codice crea quindi un <xref:System.Printing.LocalPrintServer> dell'oggetto, una classe derivata da <xref:System.Printing.PrintServer>.</span><span class="sxs-lookup"><span data-stu-id="9cea5-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="9cea5-110">Server di stampa locale è il computer in cui è in esecuzione l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9cea5-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="9cea5-111">L'ultimo passaggio significativo consiste nel passare la matrice di <xref:System.Printing.PrintServer.GetPrintQueues%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="9cea5-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="9cea5-112">Infine, i risultati vengono presentati all'utente.</span><span class="sxs-lookup"><span data-stu-id="9cea5-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="9cea5-113">È possibile estendere questo esempio con il `foreach` ciclo che scorre ogni coda di stampa ulteriormente screening.</span><span class="sxs-lookup"><span data-stu-id="9cea5-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="9cea5-114">Ad esempio, è possibile escludere le stampanti che non supportano la stampa fronte retro con la chiamata di ciclo ogni coda di stampa <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> metodo e il valore restituito di test per la presenza di stampa fronte retro.</span><span class="sxs-lookup"><span data-stu-id="9cea5-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cea5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cea5-115">See Also</span></span>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [<span data-ttu-id="9cea5-116">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="9cea5-116">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="9cea5-117">Panoramica della stampa</span><span class="sxs-lookup"><span data-stu-id="9cea5-117">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="9cea5-118">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="9cea5-118">Microsoft XPS Document Writer</span></span>](http://go.microsoft.com/fwlink/?LinkId=147319)
