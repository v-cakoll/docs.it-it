---
title: Tasti di scelta rapida per il controllo DataGrid Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- keyboard shortcuts [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], navigation keys
ms.assetid: a01780f9-20d5-4f5f-808f-c790c9a007a5
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3e80281f3a89737f060804aa5237705386232763
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="keyboard-shortcuts-for-the-windows-forms-datagrid-control"></a>Tasti di scelta rapida per il controllo DataGrid Windows Form
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Nella tabella seguente sono elencati i tasti di scelta rapida che possono essere usati per la navigazione all'interno di Windows Form <xref:System.Windows.Forms.DataGrid> controllo:  
  
|Operazione|Collegamento|  
|------------|--------------|  
|Completare l'immissione di una cella e spostarsi verso il basso alla cella successiva.<br /><br /> Se lo stato attivo è su un collegamento nella tabella figlio, passare a tale tabella.|INVIO|  
|In caso di modalità di modifica, annullare la modifica della cella.<br /><br /> In caso di selezione, annullare la modifica nella riga.|ESC|  
|Eliminare il carattere che precede il punto di inserimento quando si modifica una cella.|BACKSPACE|  
|Eliminare il carattere dopo il punto di inserimento quando si modifica una cella.|DELETE|  
|Passa alla prima cella nella riga corrente.|HOME|  
|Passa all'ultima cella nella riga corrente.|FINE|  
|Evidenziare i caratteri nella cella corrente e posizionare il cursore alla fine della riga. Stesso comportamento di doppio clic su una cella.|F2|  
|Se lo stato attivo si trova in una cella, spostarsi nella cella nella riga successiva.<br /><br /> Se lo stato attivo si trova in una riga all'ultima cella, spostare il primo collegamento per la tabella figlio della riga ed espanderlo.<br /><br /> Se lo stato attivo è su un collegamento figlio, spostare in avanti figlio.<br /><br /> Se lo stato attivo si trova sull'ultimo collegamento figlio, passare alla prima cella della riga successiva.|TAB|  
|Se lo stato attivo si trova in una cella, spostarsi sulla cella nella riga precedente.<br /><br /> Se lo stato attivo è sulla prima cella in una riga, spostarsi sull'ultimo collegamento per la tabella figlio espansi della riga precedente o spostarsi sull'ultima cella della riga precedente.<br /><br /> Se lo stato attivo è su un collegamento figlio, spostare il collegamento figlio precedente.<br /><br /> Se lo stato attivo sul primo collegamento figlio, passa all'ultima cella della riga precedente.|MAIUSC+TAB|  
|Spostare il controllo successivo nell'ordine di tabulazione.|CTRL+TAB|  
|Portarsi sul controllo precedente nell'ordine di tabulazione.|CTRL+MAIUSC+TAB|  
|Sposta su per la tabella padre in caso di una tabella figlio. Stesso comportamento facendo clic sul pulsante Indietro.|ALT+FRECCIA SINISTRA|  
|Espandere collegamenti alle tabelle figlio. ALT + freccia giù consente di espandere tutti i collegamenti, non solo quelli selezionati.|ALT + freccia giù o CTRL + segno più|  
|Comprimere i collegamenti alle tabelle figlio. ALT + freccia consente di comprimere tutti i collegamenti, non solo quelli selezionati.|ALT + freccia su o CTRL + segno meno|  
|Spostare l'ultima cella non vuota nella direzione della freccia.|CTRL + FRECCIA|  
|Estendere la riga di una selezione nella direzione della freccia (esclusi i collegamenti della tabella figlio).|MAIUSC + FRECCIA SU/GIÙ|  
|Estendere la selezione verso l'ultima riga non vuota nella direzione della freccia (esclusi i collegamenti della tabella figlio).|CTRL + MAIUSC + FRECCIA SU/GIÙ|  
|Spostarsi nella cella superiore sinistra.|CTRL + HOME|  
|Spostarsi nella cella inferiore destra.|CTRL + FINE|  
|Estendere la selezione verso la riga superiore.|CTRL + MAIUSC + HOME|  
|Estendere la selezione verso la riga inferiore.|CTRL + MAIUSC + FINE|  
|Selezionare la riga corrente (esclusi i collegamenti della tabella figlio).|MAIUSC + BARRA SPAZIATRICE|  
|Selezionare l'intera griglia (esclusi i collegamenti della tabella figlio).|CTRL+A|  
|Visualizzazione della riga padre quando in una tabella figlio.|CTRL+PGGIÙ|  
|Nascondere la riga padre quando in una tabella figlio.|CTRL+PGSU|  
|Estendere la selezione verso il basso di una schermata (esclusi i collegamenti della tabella figlio).|MAIUSC+PGGIÙ|  
|Estendere la selezione di una schermata (esclusi i collegamenti della tabella figlio).|MAIUSC+PGSU|  
|Chiamare il <xref:System.Windows.Forms.DataGrid.EndEdit%2A> metodo per la riga corrente.|CTRL+INVIO|  
|Immettere un <xref:System.DBNull.Value?displayProperty=nameWithType> valore in una cella in modalità di modifica.|CTRL+0|  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sul controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
