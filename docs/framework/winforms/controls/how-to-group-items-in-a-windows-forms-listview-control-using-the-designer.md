---
title: 'Procedura: Raggruppare elementi in un controllo di ListView Windows Form usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 4c3e20ad7a09cc21e6c1d2a6d8fbbc47d11c903d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703556"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>Procedura: Raggruppare elementi in un controllo di ListView Windows Form usando la finestra di progettazione
La caratteristica di raggruppamento del <xref:System.Windows.Forms.ListView> controllo consente di visualizzare insiemi di elementi correlati in gruppi. Questi gruppi vengono separati nella schermata dalle intestazioni del gruppo orizzontali che contengono i titoli di gruppo. È possibile usare <xref:System.Windows.Forms.ListView> gruppi per semplificare lo spostamento di elenchi di grandi dimensioni più facili raggruppando gli elementi in ordine alfabetico, per data o da qualsiasi altra forma di raggruppamento logico. L'immagine seguente mostra alcuni elementi raggruppati.  
  
 ![Gruppi ListView](./media/listviewgroups.gif "ListViewGroups")  
  
 La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.ListView> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).  
  
 Per abilitare il raggruppamento, è innanzitutto necessario creare uno o più <xref:System.Windows.Forms.ListViewGroup> gli oggetti a livello di codice o nella finestra di progettazione. Dopo aver definito un gruppo, è possibile assegnare elementi a esso.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView> i gruppi sono disponibili solo nei [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> (metodo). Nei sistemi operativi precedenti, qualsiasi codice relativo ai gruppi non ha alcun effetto e non verranno visualizzati i gruppi. Per altre informazioni, vedere <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.  
>   
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-or-remove-groups-in-the-designer"></a>Per aggiungere o rimuovere gruppi nella finestra di progettazione  
  
1.  Nel **delle proprietà** finestra, fare clic sul **puntini di sospensione** (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) accanto alla il <xref:System.Windows.Forms.ListView.Groups%2A> proprietà.  
  
     Il **Editor della raccolta ListViewGroup** viene visualizzata.  
  
2.  Per aggiungere un gruppo, scegliere il **Add** pulsante. È quindi possibile impostare le proprietà del nuovo gruppo, ad esempio la <xref:System.Windows.Forms.ListViewGroup.Header%2A> e <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> proprietà. Per rimuovere un gruppo, selezionarlo e scegliere il **rimuovere** pulsante.  
  
### <a name="to-assign-items-to-groups-in-the-designer"></a>Assegnare elementi ai gruppi nella finestra di progettazione  
  
1.  Nel **delle proprietà** finestra, fare clic sul **puntini di sospensione** (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) accanto alla il <xref:System.Windows.Forms.ListView.Items%2A> proprietà.  
  
     Il **Editor della raccolta ListViewItem** viene visualizzata.  
  
2.  Per aggiungere un nuovo elemento, scegliere il **Add** pulsante. È quindi possibile impostare le proprietà del nuovo elemento, ad esempio la <xref:System.Windows.Forms.ListViewItem.Text%2A> e <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> proprietà.  
  
3.  Selezionare il <xref:System.Windows.Forms.ListViewItem.Group%2A> proprietà e scegliere un gruppo di nell'elenco a discesa.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [Controllo ListView](listview-control-windows-forms.md)
- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
- [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
