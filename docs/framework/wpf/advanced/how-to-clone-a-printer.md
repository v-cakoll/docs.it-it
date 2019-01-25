---
title: 'Procedura: Duplicare una stampante'
ms.date: 03/30/2017
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
ms.openlocfilehash: d7a73c6590ca2df00c77a3a7255f2064a8676c42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677225"
---
# <a name="how-to-clone-a-printer"></a>Procedura: Duplicare una stampante
La maggior parte delle aziende, a un certo punto acquisti più stampanti dello stesso modello. In genere, queste vengono installate con le impostazioni di configurazione praticamente identici. L'installazione di ogni stampante può richiedere molto tempo e tendente all'errore. Il <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> dello spazio dei nomi e il <xref:System.Printing.PrintServer.InstallPrintQueue%2A> classe esposte con Microsoft .NET Framework consente di installare immediatamente un numero qualsiasi di code di stampa aggiuntive che sono stati clonati da una coda di stampa esistente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, una coda di stampa secondo viene clonata da una coda di stampa esistente. Il secondo è diverso dal primo solo nel relativo nome, posizione, porta e lo stato condiviso. I passaggi principali per eseguire questa operazione sono come indicato di seguito.  
  
1.  Creare un <xref:System.Printing.PrintQueue> oggetto per la stampante esistente che sta per essere clonata.  
  
2.  Creare un <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> dal <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> del <xref:System.Printing.PrintQueue>. Il <xref:System.Collections.DictionaryEntry.Value%2A> proprietà di ogni voce in questo dizionario è un oggetto di uno dei tipi derivati da <xref:System.Printing.IndexedProperties.PrintProperty>. Esistono due modi per impostare il valore di una voce in questo dizionario.  
  
    -   Usare il dizionario **rimuovere** e <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> metodi per rimuovere la voce e quindi aggiungerlo nuovamente con il valore desiderato.  
  
    -   Usare il dizionario <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> (metodo).  
  
     L'esempio seguente illustra entrambe le direzioni.  
  
3.  Creare un <xref:System.Printing.IndexedProperties.PrintBooleanProperty> dell'oggetto e impostare relativi <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> su "IsShared" e la relativa <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> a `true`.  
  
4.  Usare il <xref:System.Printing.IndexedProperties.PrintBooleanProperty> oggetto come valore del <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>della voce "IsShared".  
  
5.  Creare un <xref:System.Printing.IndexedProperties.PrintStringProperty> dell'oggetto e impostare relativi <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> a "Nomecondivisione" e la relativa <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> al relativo <xref:System.String>.  
  
6.  Usare la <xref:System.Printing.IndexedProperties.PrintStringProperty> oggetto come valore del <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>della voce "Nomecondivisione".  
  
7.  Creare un'altra <xref:System.Printing.IndexedProperties.PrintStringProperty> dell'oggetto e impostare relativi <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> "Posizione" e la relativa <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> al relativo <xref:System.String>.  
  
8.  Utilizzare la seconda <xref:System.Printing.IndexedProperties.PrintStringProperty> come valore dell'oggetto di <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>dell'ingresso "Percorso".  
  
9. Creare una matrice di <xref:System.String>s. Ogni elemento è il nome di una porta nel server.  
  
10. Usare <xref:System.Printing.PrintServer.InstallPrintQueue%2A> per installare la nuova stampante con i nuovi valori.  
  
 Seguito è riportato un esempio.  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [Panoramica della stampa](../../../../docs/framework/wpf/advanced/printing-overview.md)
