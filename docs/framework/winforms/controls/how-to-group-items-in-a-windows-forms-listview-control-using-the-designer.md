---
title: 'Procedura: raggruppare elementi in un controllo ListView Windows Form utilizzando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: c532cadc5b42c26f1598c4e7586309cf690456bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539342"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>Procedura: raggruppare elementi in un controllo ListView Windows Form utilizzando la finestra di progettazione
La funzionalità di raggruppamento del <xref:System.Windows.Forms.ListView> controllo consente di visualizzare i relativi set di elementi in gruppi. Questi gruppi sono separati sullo schermo dalle intestazioni del gruppo orizzontale che contengono i titoli di gruppo. È possibile utilizzare <xref:System.Windows.Forms.ListView> gruppi per semplificare lo spostamento negli elenchi di grandi dimensioni raggruppando gli elementi in ordine alfabetico, in base alla data o da qualsiasi altro raggruppamento logico. La figura seguente mostra alcuni elementi raggruppati.  
  
 ![Gruppi ListView](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
  
 La procedura seguente richiede un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.ListView> controllo. Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
 Per abilitare il raggruppamento, è innanzitutto necessario creare uno o più <xref:System.Windows.Forms.ListViewGroup> gli oggetti a livello di codice o nella finestra di progettazione. Una volta definito un gruppo, è possibile assegnare elementi a esso.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView> i gruppi sono disponibili solo nei [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> metodo. Nei sistemi operativi precedenti, qualsiasi codice relativo ai gruppi non ha alcun effetto e non verranno visualizzati i gruppi. Per altre informazioni, vedere <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.  
>   
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-or-remove-groups-in-the-designer"></a>Per aggiungere o rimuovere gruppi nella finestra di progettazione  
  
1.  Nel **proprietà** finestra, fare clic su di **i puntini di sospensione** (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al pulsante il <xref:System.Windows.Forms.ListView.Groups%2A> proprietà.  
  
     Il **Editor della raccolta ListViewGroup** viene visualizzato.  
  
2.  Per aggiungere un gruppo, fare clic su di **Aggiungi** pulsante. È quindi possibile impostare proprietà del nuovo gruppo, ad esempio il <xref:System.Windows.Forms.ListViewGroup.Header%2A> e <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> proprietà. Per rimuovere un gruppo, selezionarlo e fare clic su di **rimuovere** pulsante.  
  
### <a name="to-assign-items-to-groups-in-the-designer"></a>Per assegnare elementi ai gruppi nella finestra di progettazione  
  
1.  Nel **proprietà** finestra, fare clic su di **i puntini di sospensione** (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al pulsante il <xref:System.Windows.Forms.ListView.Items%2A> proprietà.  
  
     Il **Editor della raccolta ListViewItem** viene visualizzato.  
  
2.  Per aggiungere un nuovo elemento, fare clic su di **Aggiungi** pulsante. È quindi possibile impostare le proprietà del nuovo elemento, ad esempio il <xref:System.Windows.Forms.ListViewItem.Text%2A> e <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> proprietà.  
  
3.  Selezionare il <xref:System.Windows.Forms.ListViewItem.Group%2A> proprietà e scegliere un gruppo dall'elenco a discesa.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [Controllo ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Panoramica del controllo ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Funzionalità di Windows XP e controlli di Windows Forms](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
