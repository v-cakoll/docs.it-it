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
ms.openlocfilehash: 3e616b3b61b4b1b561d5bdb7e51525f391901a22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543589"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>Procedura: enumerare un sottoinsieme di code di stampa
Una situazione comune riscontrata da professionisti IT (IT) la gestione di un set a livello aziendale di stampanti consiste nel generare un elenco delle stampanti con determinate caratteristiche. Questa funzionalità viene fornita per il <xref:System.Printing.PrintServer.GetPrintQueues%2A> metodo di un <xref:System.Printing.PrintServer> oggetto e <xref:System.Printing.EnumeratedPrintQueueTypes> enumerazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, il codice inizia creando una matrice di flag che specificano le caratteristiche delle code di stampa che si desidera elencare. In questo esempio, si sta cercando le code di stampa vengono installate localmente nel server di stampa e condivise. Il <xref:System.Printing.EnumeratedPrintQueueTypes> enumerazione offre molte altre possibilità.  
  
 Il codice crea quindi un <xref:System.Printing.LocalPrintServer> dell'oggetto, una classe derivata da <xref:System.Printing.PrintServer>. Server di stampa locale è il computer in cui è in esecuzione l'applicazione.  
  
 L'ultimo passaggio significativo consiste nel passare la matrice di <xref:System.Printing.PrintServer.GetPrintQueues%2A> metodo.  
  
 Infine, i risultati vengono presentati all'utente.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 È possibile estendere questo esempio con il `foreach` ciclo che scorre ogni coda di stampa ulteriormente screening. Ad esempio, è possibile escludere le stampanti che non supportano la stampa fronte retro con la chiamata di ciclo ogni coda di stampa <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> metodo e il valore restituito di test per la presenza di stampa fronte retro.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Panoramica della stampa](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319)
