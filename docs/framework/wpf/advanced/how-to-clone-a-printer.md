---
title: 'Procedura: duplicare una stampante'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9ffb9f5ab8e7b768d888f5f2800fae668e47bfc3
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-clone-a-printer"></a>Procedura: duplicare una stampante
A un certo punto, la maggior parte delle aziende acquisterà più stampanti dello stesso modello. In genere, questi vengono installati con le impostazioni di configurazione praticamente identico. Installazione di ogni stampante può richiedere molto tempo e soggetta a errori. Il <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> spazio dei nomi e il <xref:System.Printing.PrintServer.InstallPrintQueue%2A> classe esposta con Microsoft .NET Framework consente di installare immediatamente qualsiasi numero di code di stampa aggiuntive che vengono clonati da una coda di stampa esistente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, viene duplicata una seconda coda di stampa da una coda di stampa esistente. Il secondo è diverso dal primo solo nel relativo nome, percorso, porta e lo stato condiviso. Come indicato di seguito sono riportati i passaggi principali per eseguire questa operazione.  
  
1.  Creare un <xref:System.Printing.PrintQueue> oggetto per la stampante esistente che sta per essere clonata.  
  
2.  Creare un <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> dal <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> del <xref:System.Printing.PrintQueue>. Il <xref:System.Collections.DictionaryEntry.Value%2A> proprietà di ciascuna voce del dizionario è un oggetto di uno dei tipi derivati da <xref:System.Printing.IndexedProperties.PrintProperty>. Esistono due modi per impostare il valore di una voce nel dizionario.  
  
    -   Utilizzare il dizionario **rimuovere** e <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> metodi per rimuovere la voce e quindi aggiungerlo nuovamente con il valore desiderato.  
  
    -   Utilizzare il dizionario <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> metodo.  
  
     Nell'esempio seguente vengono illustrate entrambe le direzioni.  
  
3.  Creare un <xref:System.Printing.IndexedProperties.PrintBooleanProperty> e impostare il relativo <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> su "IsShared" e il relativo <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> a `true`.  
  
4.  Utilizzare il <xref:System.Printing.IndexedProperties.PrintBooleanProperty> oggetto come valore del <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>della voce "IsShared".  
  
5.  Creare un <xref:System.Printing.IndexedProperties.PrintStringProperty> e impostare il relativo <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> per "Nomecondivisione" e il relativo <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> al relativo <xref:System.String>.  
  
6.  Utilizzare il <xref:System.Printing.IndexedProperties.PrintStringProperty> oggetto come valore del <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>della voce "Nomecondivisione".  
  
7.  Creare un altro <xref:System.Printing.IndexedProperties.PrintStringProperty> e impostare il relativo <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> "Posizione" e il relativo <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> al relativo <xref:System.String>.  
  
8.  Utilizzare la seconda <xref:System.Printing.IndexedProperties.PrintStringProperty> oggetto come valore del <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>della voce "Location".  
  
9. Creare una matrice di <xref:System.String>s. Ogni elemento è il nome di una porta nel server.  
  
10. Utilizzare <xref:System.Printing.PrintServer.InstallPrintQueue%2A> per installare la nuova stampante con i nuovi valori.  
  
 Un esempio è inferiore.  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Panoramica della stampa](../../../../docs/framework/wpf/advanced/printing-overview.md)
