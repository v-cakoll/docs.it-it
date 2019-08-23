---
title: Cenni preliminari sul controllo ListView (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
ms.openlocfilehash: 7b7eac942a7e857ad731c0f77389e84aee287c08
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952160"
---
# <a name="listview-control-overview-windows-forms"></a>Cenni preliminari sul controllo ListView (Windows Form)
Il controllo <xref:System.Windows.Forms.ListView> di Windows Forms visualizza un elenco di elementi con icone. È possibile usare una visualizzazione elenco per creare un'interfaccia utente simile al riquadro destro di Esplora risorse. Il controllo dispone di quattro modalità di visualizzazione: LargeIcon, SmallIcon, List e Details.  
  
## <a name="what-you-can-do-with-the-listview-control"></a>Operazioni possibili con il controllo ListView  
  
> [!NOTE]
> Una modalità di visualizzazione aggiuntiva, affiancata, è disponibile solo in Windows XP e nel sistema operativo Windows Server 2003. Per altre informazioni, vedere [Procedura: Abilitare la visualizzazione affiancata in un controllo](how-to-enable-tile-view-in-a-windows-forms-listview-control.md)ListView Windows Forms.  
  
 La modalità LargeIcon visualizza icone grandi accanto al testo dell'elemento; gli elementi vengono visualizzati in più colonne se il controllo è sufficientemente grande. La modalità SmallIcon è la stessa, ad eccezione del fatto che Visualizza icone piccole. La modalità elenco Visualizza icone piccole ma si trova sempre in un'unica colonna. La modalità dettagli Visualizza gli elementi in più colonne. Per informazioni dettagliate, vedere [Procedura: Aggiungere colonne al controllo](how-to-add-columns-to-the-windows-forms-listview-control.md)ListView Windows Forms. La modalità di visualizzazione è determinata dalla <xref:System.Windows.Forms.ListView.View%2A> proprietà. Tutte le modalità di visualizzazione possono visualizzare immagini da elenchi di immagini. Per informazioni dettagliate, vedere [Procedura: Visualizza le icone per il controllo](how-to-display-icons-for-the-windows-forms-listview-control.md)ListView Windows Forms.  
  
 Nella tabella seguente sono elencati alcuni dei <xref:System.Windows.Forms.ListView> membri e le visualizzazioni in cui sono validi.  
  
|Membro ListView|Visualizza|  
|---------------------|----------|  
|Proprietà <xref:System.Windows.Forms.ListView.Alignment%2A>|<xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>|  
|Proprietà <xref:System.Windows.Forms.ListView.AutoArrange%2A>|<xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>|  
|Metodo <xref:System.Windows.Forms.ListView.AutoResizeColumn%2A>|<xref:System.Windows.Forms.View.Details>|  
|Proprietà <xref:System.Windows.Forms.ListView.Columns%2A>|<xref:System.Windows.Forms.View.Details> o <xref:System.Windows.Forms.View.Tile>|  
|Evento<xref:System.Windows.Forms.ListView.DrawSubItem>|<xref:System.Windows.Forms.View.Details>|  
|Metodo <xref:System.Windows.Forms.ListView.FindItemWithText%2A>|<xref:System.Windows.Forms.View.Details>, <xref:System.Windows.Forms.View.List>o <xref:System.Windows.Forms.View.Tile>|  
|Metodo <xref:System.Windows.Forms.ListView.FindNearestItem%2A>|<xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>|  
|Metodo <xref:System.Windows.Forms.ListView.GetItemAt%2A>|<xref:System.Windows.Forms.View.Details> o <xref:System.Windows.Forms.View.Tile>|  
|Proprietà <xref:System.Windows.Forms.ListView.Groups%2A>|Tutte le visualizzazioni eccetto<xref:System.Windows.Forms.View.List>|  
|Proprietà <xref:System.Windows.Forms.ListView.HeaderStyle%2A>|[https://login.microsoftonline.com/common/](<xref:System.Windows.Forms.View.Details>).|  
|Proprietà <xref:System.Windows.Forms.ListView.InsertionMark%2A>|<xref:System.Windows.Forms.View.LargeIcon>, <xref:System.Windows.Forms.View.SmallIcon>o <xref:System.Windows.Forms.View.Tile>|  
  
 La proprietà chiave del <xref:System.Windows.Forms.ListView> controllo è <xref:System.Windows.Forms.ListView.Items%2A>, che contiene gli elementi visualizzati dal controllo. La <xref:System.Windows.Forms.ListView.SelectedItems%2A> proprietà contiene una raccolta degli elementi attualmente selezionati nel controllo. L'utente può selezionare più elementi, ad esempio per trascinare e rilasciare più elementi alla volta in un altro controllo, se la <xref:System.Windows.Forms.ListView.MultiSelect%2A> proprietà è impostata su `true`. Se <xref:System.Windows.Forms.ListView> la <xref:System.Windows.Forms.ListView.CheckBoxes%2A> proprietà è impostata su `true`, il controllo può visualizzare le caselle di controllo accanto agli elementi.  
  
 La <xref:System.Windows.Forms.ListView.Activation%2A> proprietà determina il tipo di azione che l'utente deve eseguire per attivare un elemento nell'elenco: le opzioni sono <xref:System.Windows.Forms.ItemActivation.Standard>, <xref:System.Windows.Forms.ItemActivation.OneClick>e <xref:System.Windows.Forms.ItemActivation.TwoClick>. <xref:System.Windows.Forms.ItemActivation.OneClick>l'attivazione richiede un solo clic per attivare l'elemento. <xref:System.Windows.Forms.ItemActivation.TwoClick>l'attivazione richiede che l'utente faccia doppio clic per attivare l'elemento; un singolo clic modifica il colore del testo dell'elemento. <xref:System.Windows.Forms.ItemActivation.Standard>l'attivazione richiede che l'utente faccia doppio clic per attivare un elemento, ma l'elemento non cambia aspetto.  
  
 Il <xref:System.Windows.Forms.ListView> controllo supporta inoltre gli stili di visualizzazione e altre funzionalità disponibili sulla piattaforma Windows XP, inclusi il raggruppamento, la visualizzazione affiancata e i contrassegni di inserimento.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- [Controllo ListView](listview-control-windows-forms.md)
- [Procedura: Aggiungere e rimuovere elementi con il controllo ListView Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Procedura: Aggiunta di colonne al controllo Windows Forms ListView](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Procedura: Visualizzare le icone per il controllo ListView Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Procedura: Visualizzare gli elementi secondari nelle colonne con il controllo ListView Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Procedura: Seleziona un elemento nel controllo Windows Forms ListView](how-to-select-an-item-in-the-windows-forms-listview-control.md)
- [Procedura: Raggruppare elementi in un controllo ListView Windows Forms](how-to-group-items-in-a-windows-forms-listview-control.md)
- [Procedura: Visualizza un segno di inserimento in un controllo ListView Windows Forms](how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)
- [Procedura: Aggiungere funzionalità di ricerca a un controllo ListView](how-to-add-search-capabilities-to-a-listview-control.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Procedura: Creare un'interfaccia utente a più riquadri con Windows Forms](how-to-create-a-multipane-user-interface-with-windows-forms.md)
