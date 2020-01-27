---
title: Tasti di scelta rapida per il controllo DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard shortcuts [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], navigation keys
ms.assetid: a01780f9-20d5-4f5f-808f-c790c9a007a5
ms.openlocfilehash: 6693531b8d0e820a68d75bf5da40f4169fd244f2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745034"
---
# <a name="keyboard-shortcuts-for-the-windows-forms-datagrid-control"></a>Tasti di scelta rapida per il controllo DataGrid Windows Form
> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Nella tabella seguente sono elencati i tasti di scelta rapida che è possibile usare per la navigazione all'interno del Windows Forms controllo <xref:System.Windows.Forms.DataGrid>:  
  
|Azione|Collegamento|  
|------------|--------------|  
|Completa una voce di cella e Sposta giù nella cella successiva.<br /><br /> Se lo stato attivo si trova in un collegamento alla tabella figlio, passare a tale tabella.|INVIO|  
|Annulla la modifica della cella se in modalità di modifica della cella.<br /><br /> Se nella selezione Marquee, annullare la modifica sulla riga.|ESC|  
|Elimina il carattere prima del punto di inserimento durante la modifica di una cella.|BACKSPACE|  
|Elimina il carattere dopo il punto di inserimento durante la modifica di una cella.|DELETE|  
|Passa alla prima cella della riga corrente.|HOME|  
|Passa all'ultima cella della riga corrente.|FINE|  
|Evidenziare i caratteri nella cella corrente e posizionare il punto di inserimento alla fine della riga. Lo stesso comportamento che si fa doppio clic su una cella.|F2|  
|Se lo stato attivo si trova su una cella, passare alla cella successiva nella riga.<br /><br /> Se lo stato attivo è sull'ultima cella in una riga, spostarsi sul primo collegamento della tabella figlio della riga ed espanderlo.<br /><br /> Se lo stato attivo si trova su un collegamento figlio, passare al collegamento figlio successivo.<br /><br /> Se lo stato attivo è sull'ultimo collegamento figlio, passare alla prima cella della riga successiva.|TAB|  
|Se lo stato attivo si trova su una cella, passare alla cella precedente della riga.<br /><br /> Se lo stato attivo si trova nella prima cella di una riga, passare all'ultimo collegamento della tabella figlio espanso della riga precedente oppure passare all'ultima cella della riga precedente.<br /><br /> Se lo stato attivo si trova su un collegamento figlio, passare al collegamento figlio precedente.<br /><br /> Se lo stato attivo si trova sul primo collegamento figlio, passare all'ultima cella della riga precedente.|MAIUSC + TAB|  
|Passare al controllo successivo nell'ordine di tabulazione.|CTRL + TAB|  
|Passare al controllo precedente nell'ordine di tabulazione.|CTRL+MAIUSC+TAB|  
|Spostarsi fino alla tabella padre se è presente in una tabella figlio. Lo stesso comportamento della selezione del pulsante indietro.|ALT+FRECCIA SINISTRA|  
|Espandere collegamenti tabella figlio. ALT + freccia giù espande tutti i collegamenti, non solo quelli selezionati.|ALT + freccia giù o CTRL + segno più|  
|Comprime i collegamenti alla tabella figlio. ALT + freccia su comprime tutti i collegamenti, non solo quelli selezionati.|ALT + freccia su o CTRL + segno meno|  
|Passare alla cella non vuota più lontana nella direzione della freccia.|CTRL + freccia|  
|Estendere la selezione di una riga nella direzione della freccia (esclusi i collegamenti alla tabella figlio).|MAIUSC + FRECCIA SU/GIÙ|  
|Estendere la selezione alla riga non vuota più lontana nella direzione della freccia (esclusi i collegamenti alla tabella figlio).|CTRL + MAIUSC + FRECCIA SU/GIÙ|  
|Spostarsi nella cella in alto a sinistra.|CTRL + HOME|  
|Spostarsi nella cella inferiore destra.|CTRL + fine|  
|Estendere la selezione alla riga superiore.|CTRL + MAIUSC + HOME|  
|Estendere la selezione alla riga inferiore.|CTRL + MAIUSC + fine|  
|Consente di selezionare la riga corrente (esclusi i collegamenti alla tabella figlio).|MAIUSC + barra SPAZIAtrice|  
|Selezionare l'intera griglia (esclusi i collegamenti alla tabella figlio).|CTRL+A|  
|Visualizza la riga padre quando si è in una tabella figlio.|CTRL+PGGIÙ|  
|Nascondere la riga padre quando si è in una tabella figlio.|CTRL+PGSU|  
|Estendere la selezione verso il basso di una schermata (esclusi i collegamenti alla tabella figlio).|MAIUSC+PGGIÙ|  
|Estendere la selezione verso l'alto di una schermata (esclusi i collegamenti alla tabella figlio).|MAIUSC+PGSU|  
|Chiamare il metodo <xref:System.Windows.Forms.DataGrid.EndEdit%2A> per la riga corrente.|CTRL+INVIO|  
|Immettere un valore <xref:System.DBNull.Value?displayProperty=nameWithType> in una cella in modalità di modifica.|CTRL+0|  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sul controllo DataGrid](datagrid-control-overview-windows-forms.md)
- [Controllo DataGrid](datagrid-control-windows-forms.md)
