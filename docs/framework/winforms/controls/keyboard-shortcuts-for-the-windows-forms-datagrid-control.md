---
title: Tasti di scelta rapida per il controllo DataGrid Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard shortcuts [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], navigation keys
ms.assetid: a01780f9-20d5-4f5f-808f-c790c9a007a5
ms.openlocfilehash: c04340cf2d2c8e318ea7348c978ef943563c24da
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711772"
---
# <a name="keyboard-shortcuts-for-the-windows-forms-datagrid-control"></a>Tasti di scelta rapida per il controllo DataGrid Windows Form
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 La tabella seguente elenca i tasti di scelta rapida che possono essere utilizzati per la navigazione all'interno di moduli di Windows <xref:System.Windows.Forms.DataGrid> controllo:  
  
|Operazione|Collegamento|  
|------------|--------------|  
|Completare una voce di cella e spostare verso il basso alla cella successiva.<br /><br /> Se lo stato attivo è su un collegamento nella tabella figlio, passare a tale tabella.|INVIO|  
|Se in modalità di modifica di cella, annullare la modifica della cella.<br /><br /> In caso di selezione, annullare la modifica nella riga.|ESC|  
|Eliminare il carattere che precede il punto di inserimento quando si modifica una cella.|BACKSPACE|  
|Eliminare i caratteri dopo il punto di inserimento quando si modifica una cella.|DELETE|  
|Passa alla prima cella nella riga corrente.|HOME|  
|Passa all'ultima cella nella riga corrente.|FINE|  
|Evidenziare i caratteri nella cella corrente e posizionare il cursore alla fine della riga. Stesso comportamento di doppio clic su una cella.|F2|  
|Se lo stato attivo è su una cella, passare alla cella nella riga successiva.<br /><br /> Se lo stato attivo è sull'ultima cella in una riga, spostare il primo collegamento nella tabella figlio della riga ed espanderlo.<br /><br /> Se lo stato attivo è su un collegamento figlio, spostare il successivo collegamento figlio.<br /><br /> Se è attiva l'ultimo collegamento figlio, passare alla prima cella della riga successiva.|TAB|  
|Se lo stato attivo è su una cella, spostarsi sulla cella nella riga precedente.<br /><br /> Se lo stato attivo è sulla prima cella in una riga, spostare l'ultimo collegamento per la tabella figlio espansa della riga precedente o spostarsi sull'ultima cella della riga precedente.<br /><br /> Se lo stato attivo è su un collegamento figlio, spostare il collegamento figlio precedente.<br /><br /> Se lo stato attivo si trova il primo collegamento figlio, passa all'ultima cella della riga precedente.|MAIUSC+TAB|  
|Spostare il controllo successivo nell'ordine di tabulazione.|CTRL+TAB|  
|Spostare il controllo precedente nell'ordine di tabulazione.|CTRL+MAIUSC+TAB|  
|Spostato in alto alla tabella padre in caso di una tabella figlio. Stesso comportamento facendo clic sul pulsante Indietro.|ALT+FRECCIA SINISTRA|  
|Espandere collegamenti della tabella figlio. ALT + freccia giù espande tutti i collegamenti, non solo quelli selezionati.|ALT + freccia giù o CTRL + segno più|  
|Comprime i collegamenti nella tabella figlio. ALT + freccia consente di comprimere tutti i collegamenti, non solo quelli selezionati.|ALT + freccia su o CTRL + segno meno|  
|Spostare l'ultima cella non vuota nella direzione della freccia.|CTRL + TASTI DI DIREZIONE|  
|Estendere la riga di una selezione nella direzione della freccia (esclusi i collegamenti della tabella figlio).|MAIUSC + FRECCIA SU/FRECCIA GIÙ|  
|Estendere la selezione per l'ultima riga non vuota nella direzione della freccia (esclusi i collegamenti della tabella figlio).|CTRL + MAIUSC + FRECCIA SU/FRECCIA GIÙ|  
|Spostarsi nella cella superiore sinistra.|CTRL+HOME|  
|Spostarsi nella cella inferiore destro.|CTRL + FINE|  
|Estendere la selezione alla riga superiore.|CTRL + MAIUSC + HOME|  
|Estendere la selezione per la riga inferiore.|CTRL + MAIUSC + END|  
|Selezionare la riga corrente (esclusi i collegamenti della tabella figlio).|MAIUSC + BARRA SPAZIATRICE|  
|Selezionare l'intera griglia (esclusi i collegamenti della tabella figlio).|CTRL+A|  
|Visualizzare la riga padre quando in una tabella figlio.|CTRL+PGGIÙ|  
|Nascondere la riga padre quando in una tabella figlio.|CTRL+PGSU|  
|Estendere la selezione verso il basso una sola schermata (esclusi i collegamenti della tabella figlio).|MAIUSC+PGGIÙ|  
|Estendere la selezione alla schermata precedente (esclusi i collegamenti della tabella figlio).|MAIUSC+PGSU|  
|Chiamare il <xref:System.Windows.Forms.DataGrid.EndEdit%2A> metodo per la riga corrente.|CTRL+INVIO|  
|Immettere un <xref:System.DBNull.Value?displayProperty=nameWithType> valore in una cella in modalità di modifica.|CTRL+0|  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sul controllo DataGrid](datagrid-control-overview-windows-forms.md)
- [Controllo DataGrid](datagrid-control-windows-forms.md)
