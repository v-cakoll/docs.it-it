---
title: Cenni preliminari sul controllo ListView (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b79fecb0a537f4c568b4a57e9ce2bfab8d8e1005
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="listview-control-overview-windows-forms"></a>Cenni preliminari sul controllo ListView (Windows Form)
Il controllo <xref:System.Windows.Forms.ListView> di Windows Forms visualizza un elenco di elementi con icone. È possibile usare una visualizzazione elenco per creare un'interfaccia utente simile al riquadro destro di Esplora risorse. Il controllo dispone di quattro modalità di visualizzazione: LargeIcon, SmallIcon, elenco e dettagli.  
  
## <a name="what-you-can-do-with-the-listview-control"></a>Cosa si può fare con il controllo ListView  
  
> [!NOTE]
>  Modalità di visualizzazione aggiuntiva, riquadro, è disponibile solo in Windows XP e il sistema operativo Windows Server 2003. Per ulteriori informazioni, vedere [procedura: abilitare la visualizzazione affiancata in un controllo ListView Windows Form](../../../../docs/framework/winforms/controls/how-to-enable-tile-view-in-a-windows-forms-listview-control.md).  
  
 La modalità LargeIcon visualizza icone grandi accanto al testo dell'elemento; gli elementi visualizzati in più colonne, se il controllo è sufficientemente grande. La modalità SmallIcon è uguale ad eccezione del fatto che vengano visualizzate icone piccole. La modalità elenco vengono visualizzate icone di piccole dimensioni, ma è sempre in una singola colonna. La modalità dei dettagli Visualizza gli elementi in più colonne. Per informazioni dettagliate, vedere [procedura: aggiungere colonne al controllo ListView Windows Form](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md). La modalità di visualizzazione è determinata dal <xref:System.Windows.Forms.ListView.View%2A> proprietà. Tutte le modalità di visualizzazione di visualizzare le immagini da elenchi di immagini. Per informazioni dettagliate, vedere [procedura: visualizzare icone per il controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md).  
  
 Nella tabella seguente sono elencate alcune delle <xref:System.Windows.Forms.ListView> membri e le viste sono validi in.  
  
|Membro di ListView|Visualizza|  
|---------------------|----------|  
|Proprietà <xref:System.Windows.Forms.ListView.Alignment%2A>|<xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>|  
|Proprietà <xref:System.Windows.Forms.ListView.AutoArrange%2A>|<xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>|  
|Metodo <xref:System.Windows.Forms.ListView.AutoResizeColumn%2A>|<xref:System.Windows.Forms.View.Details>|  
|Proprietà <xref:System.Windows.Forms.ListView.Columns%2A>|<xref:System.Windows.Forms.View.Details> o <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.DrawSubItem>evento|<xref:System.Windows.Forms.View.Details>|  
|Metodo <xref:System.Windows.Forms.ListView.FindItemWithText%2A>|<xref:System.Windows.Forms.View.Details>, <xref:System.Windows.Forms.View.List>o <xref:System.Windows.Forms.View.Tile>|  
|Metodo <xref:System.Windows.Forms.ListView.FindNearestItem%2A>|<xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>|  
|Metodo <xref:System.Windows.Forms.ListView.GetItemAt%2A>|<xref:System.Windows.Forms.View.Details> o <xref:System.Windows.Forms.View.Tile>|  
|Proprietà <xref:System.Windows.Forms.ListView.Groups%2A>|Tutte le visualizzazioni tranne<xref:System.Windows.Forms.View.List>|  
|Proprietà <xref:System.Windows.Forms.ListView.HeaderStyle%2A>|<xref:System.Windows.Forms.View.Details>.|  
|Proprietà <xref:System.Windows.Forms.ListView.InsertionMark%2A>|<xref:System.Windows.Forms.View.LargeIcon>, <xref:System.Windows.Forms.View.SmallIcon>o <xref:System.Windows.Forms.View.Tile>|  
  
 La proprietà chiave di <xref:System.Windows.Forms.ListView> controllo <xref:System.Windows.Forms.ListView.Items%2A>, che contiene gli elementi visualizzati dal controllo. Il <xref:System.Windows.Forms.ListView.SelectedItems%2A> proprietà contiene una raccolta degli elementi attualmente selezionati nel controllo. L'utente può selezionare più elementi, ad esempio trascinamento contemporaneamente in un altro controllo, se il <xref:System.Windows.Forms.ListView.MultiSelect%2A> è impostata su `true`. Il <xref:System.Windows.Forms.ListView> controllo può visualizzare caselle di controllo accanto agli elementi, se il <xref:System.Windows.Forms.ListView.CheckBoxes%2A> è impostata su `true`.  
  
 Il <xref:System.Windows.Forms.ListView.Activation%2A> proprietà determina il tipo di operazione da effettuare per attivare un elemento nell'elenco: le opzioni sono <xref:System.Windows.Forms.ItemActivation.Standard>, <xref:System.Windows.Forms.ItemActivation.OneClick>, e <xref:System.Windows.Forms.ItemActivation.TwoClick>. <xref:System.Windows.Forms.ItemActivation.OneClick>l'attivazione richiede un solo clic per attivare l'elemento. <xref:System.Windows.Forms.ItemActivation.TwoClick>attivazione richiede all'utente di fare doppio clic per attivare l'elemento. un solo clic modifica il colore del testo dell'elemento. <xref:System.Windows.Forms.ItemActivation.Standard>attivazione richiede all'utente di fare doppio clic per attivare un elemento, ma l'elemento non viene modificato l'aspetto.  
  
 Il <xref:System.Windows.Forms.ListView> controllo supporta inoltre gli stili e altre funzionalità disponibili nella piattaforma Windows XP, inclusi il raggruppamento, la visualizzazione affiancata e segni di inserimento. Per ulteriori informazioni, vedere [funzionalità di Windows XP e controlli Windows Form](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ListView>  
 [Controllo ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [Procedura: Aggiungere colonne al controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [Procedura: Visualizzare icone per il controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [Procedura: Visualizzare elementi secondari nelle colonne con il controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 [Procedura: Selezionare un elemento nel controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-select-an-item-in-the-windows-forms-listview-control.md)  
 [Procedura: Raggruppare elementi in un controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)  
 [Procedura: Visualizzare un segno di inserimento in un controllo ListView per Windows Form](../../../../docs/framework/winforms/controls/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)  
 [Procedura: Aggiungere funzionalità di ricerca a un controllo ListView](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
 [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [Procedura: Creare un'interfaccia utente a più riquadri con Windows Form](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)
