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
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>Procedura: enumerare un sottoinsieme di code di stampa
Una situazione comune affrontata dai professionisti IT (Information Technology) che gestiscono un set di stampanti a livello aziendale consiste nel generare un elenco di stampanti con determinate caratteristiche. Questa funzionalità viene fornita dal metodo <xref:System.Printing.PrintServer.GetPrintQueues%2A> di un oggetto <xref:System.Printing.PrintServer> e dall'enumerazione <xref:System.Printing.EnumeratedPrintQueueTypes>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente il codice inizia creando una matrice di flag che specificano le caratteristiche delle code di stampa che si desidera elencare. In questo esempio, si stanno cercando le code di stampa installate localmente nel server di stampa e condivise. L'enumerazione <xref:System.Printing.EnumeratedPrintQueueTypes> offre molte altre possibilità.  
  
 Il codice crea quindi un oggetto <xref:System.Printing.LocalPrintServer>, una classe derivata da <xref:System.Printing.PrintServer>. Il server di stampa locale è il computer in cui è in esecuzione l'applicazione.  
  
 L'ultimo passaggio significativo consiste nel passare la matrice al metodo <xref:System.Printing.PrintServer.GetPrintQueues%2A>.  
  
 Infine, i risultati vengono presentati all'utente.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 Questo esempio può essere esteso con il ciclo di `foreach` che esegue l'analisi di ogni coda di stampa. Ad esempio, è possibile escludere le stampanti che non supportano la stampa su due lati, facendo in modo che il ciclo chiami il metodo <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> della coda di stampa e testando il valore restituito per la presenza di duplexing.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Documenti in WPF](documents-in-wpf.md)
- [Panoramica della stampa](printing-overview.md)
- [Microsoft XPS Document Writer](/windows/win32/printdocs/microsoft-xps-document-writer)
