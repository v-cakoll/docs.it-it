---
title: 'Procedura: Convalidare e unire PrintTicke'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
ms.openlocfilehash: 0b9f7b101ea4f06c86f66f8e4e16d1ffeabaa9e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671941"
---
# <a name="how-to-validate-and-merge-printtickets"></a>Procedura: Convalidare e unire PrintTicke
Il [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [printschema](https://go.microsoft.com/fwlink/?LinkId=186397) include flessibili ed estensibili <xref:System.Printing.PrintCapabilities> e <xref:System.Printing.PrintTicket> elementi. Il primo indica in modo dettagliato le funzionalità di un dispositivo di stampa e specifica il secondo modo in cui il dispositivo deve usare tali funzionalità rispetto a una determinata sequenza di documenti, singoli documenti o singola pagina.  
  
 Una tipica sequenza di attività per un'applicazione che supporta la stampa sarebbe come indicato di seguito.  
  
1.  Determinare le funzionalità della stampante.  
  
2.  Configurare un <xref:System.Printing.PrintTicket> usare tali funzionalità.  
  
3.  Convalidare il <xref:System.Printing.PrintTicket>.  
  
 Questo articolo illustra come eseguire questa operazione.  
  
## <a name="example"></a>Esempio  
 Nel semplice esempio seguente, si è interessati solo se una stampante può supportare la stampa fronte retro-stampa fronte retro. Come indicato di seguito sono riportati i passaggi principali.  
  
1.  Ottenere un <xref:System.Printing.PrintCapabilities> dell'oggetto con il <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> (metodo).  
  
2.  Verificare la presenza della funzionalità desiderata. Nell'esempio seguente, viene eseguito il test di <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> proprietà del <xref:System.Printing.PrintCapabilities> la presenza di funzionalità di stampa su entrambi i lati di un foglio di carta con la"pagina" dell'oggetto sul lato lungo del foglio. Poiché <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> è una raccolta, usiamo il `Contains` metodo <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.  
  
    > [!NOTE]
    >  Questo passaggio non è strettamente necessario. Il <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> metodo seguente verificherà ogni richiesta <xref:System.Printing.PrintTicket> rispetto alle funzionalità della stampante. Se la funzionalità richiesta non è supportata dalla stampante, il driver della stampante consente di sostituire una richiesta in alternativa il <xref:System.Printing.PrintTicket> restituito dal metodo.  
  
3.  Se la stampante supporta la stampa fronte retro, il codice di esempio crea un <xref:System.Printing.PrintTicket> che richiede la stampa fronte retro. Ma l'applicazione non specifica ogni stampante possibili impostazione disponibile nel <xref:System.Printing.PrintTicket> elemento. Sarebbe dispendioso di programmatore e ora del programma. Al contrario, il codice imposta solo la richiesta di stampa fronte retro e quindi unisce questo <xref:System.Printing.PrintTicket> con un oggetto esistente, completamente configurata e convalidata <xref:System.Printing.PrintTicket>, in questo caso, predefinita dell'utente <xref:System.Printing.PrintTicket>.  
  
4.  Di conseguenza, l'esempio chiama il <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> per unire il nuovo metodo minima in quando <xref:System.Printing.PrintTicket> predefinito dell'utente <xref:System.Printing.PrintTicket>. Restituisce un <xref:System.Printing.ValidationResult> che include il nuovo <xref:System.Printing.PrintTicket> come una delle relative proprietà.  
  
5.  L'esempio verifica quindi che il nuovo <xref:System.Printing.PrintTicket> richiede la stampa fronte retro. In caso affermativo, quindi l'esempio rende il nuovo print ticket per l'utente predefinito. Se viene omesso il passaggio 2 precedente e la stampante non supporta la stampa fronte retro lungo il lato lungo, quindi il test avrebbe comportato `false`. (Vedere la nota precedente).  
  
6.  L'ultimo elemento significativo è eseguire il commit per la modifica di <xref:System.Printing.PrintQueue.UserPrintTicket%2A> proprietà del <xref:System.Printing.PrintQueue> con il <xref:System.Printing.PrintQueue.Commit%2A> (metodo).  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 In modo che è possibile testare rapidamente in questo esempio, la parte restante viene presentata di seguito. Creare un progetto e uno spazio dei nomi e quindi incollare entrambi i frammenti di codice in questo articolo il blocco dello spazio dei nomi.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [Panoramica della stampa](../../../../docs/framework/wpf/advanced/printing-overview.md)
- [Schema di stampa](https://go.microsoft.com/fwlink/?LinkId=186397)
