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
ms.openlocfilehash: bf45d6fb3fb161ca5171e94b9ab7af1e0e6f0c3d
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43786941"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>Procedura: enumerare un sottoinsieme di code di stampa
Una situazione comune affrontata dai professionisti informatici (IT) gestisce un set a livello aziendale delle stampanti consiste nel generare un elenco delle stampanti con determinate caratteristiche. Questa funzionalità viene fornita per il <xref:System.Printing.PrintServer.GetPrintQueues%2A> metodo di un <xref:System.Printing.PrintServer> oggetto e il <xref:System.Printing.EnumeratedPrintQueueTypes> enumerazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, il codice inizia creando una matrice di flag che specificano le caratteristiche delle code di stampa che si desidera elencare. In questo esempio, si ricercano le code di stampa che vengono installate localmente nei server di stampa e sono condivisi. Il <xref:System.Printing.EnumeratedPrintQueueTypes> enumerazione fornisce molte altre possibilità.  
  
 Il codice crea quindi una <xref:System.Printing.LocalPrintServer> dell'oggetto, una classe derivata da <xref:System.Printing.PrintServer>. Il server di stampa locale è il computer in cui viene eseguita l'applicazione.  
  
 L'ultimo passaggio significativo consiste nel passare la matrice di <xref:System.Printing.PrintServer.GetPrintQueues%2A> (metodo).  
  
 Infine, i risultati vengono presentati all'utente.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 È possibile estendere questo esempio facendo in modo che il `foreach` ciclo che eseguire ulteriori passaggi attraverso ogni coda di stampa screening. Ad esempio, è possibile escludere le stampanti che non supportano la stampa fronte retro facendo in modo che la chiamata di ciclo ogni coda di stampa <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> metodo ed eseguire test del valore restituito per la presenza di stampa fronte retro.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Panoramica della stampa](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319)
