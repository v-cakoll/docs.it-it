---
title: 'Procedura: creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 02f98cce74f99d8a00bc916b38e5c290045926a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a>Procedura: creare un form Master-Details mediante due controlli DataRepeater (Visual Studio)
È possibile visualizzare dati correlati utilizzando due o più <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controlli per creare un form master-details. Potrebbe ad esempio, si desidera visualizzare un elenco di clienti in uno <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>e quando l'utente seleziona un cliente, è possibile visualizzare un elenco di ordini del cliente in un secondo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
 È possibile visualizzare dati correlati trascinando gli elementi di dettaglio che condividono lo stesso nodo di tabella master dal **origini dati** finestra un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Ad esempio, se si dispone di un'origine dati che dispone di una tabella Customers e una tabella correlata Orders, vedrai entrambe le tabelle come nodi di primo livello nella visualizzazione struttura ad albero di **origini dati** finestra. Espandere il nodo di clienti in modo che è possibile visualizzare le colonne. Si noti che l'ultima colonna nell'elenco è un nodo che rappresenta la tabella Orders. Questo nodo rappresenta gli ordini relativi a un cliente.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a>Per visualizzare dati correlati in due controlli DataRepeater  
  
1.  Trascinare due <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> dei controlli di **Visual Basic Power Packs** nella scheda il **della casella degli strumenti** a un controllo form o del contenitore.  
  
2.  Trascinare i quadratini di ridimensionamento e la posizione per ridimensionare i controlli e posizionarli side-by-side.  
  
3.  Scegliere **Mostra origini dati** dal menu **Dati**.  
  
    > [!NOTE]
    >  Se il **origini dati** finestra è vuota, aggiungere un'origine dati. Per altre informazioni, vedere [Add new data sources](/visualstudio/data-tools/add-new-data-sources) (Aggiungere nuove origini dati).  
  
4.  Nel **origini dati** finestra, selezionare il nodo di livello superiore per la tabella master.  
  
5.  Modificare il tipo di rilascio della tabella master per i dettagli, fare clic su **dettagli** nell'elenco a discesa nel nodo della tabella.  
  
6.  Trascinare il nodo di tabella master area modello dell'elemento del primo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
7.  Espandere il nodo della tabella master e selezionare il nodo dettaglio della tabella correlata.  
  
8.  Modificare il tipo di rilascio della tabella dettagli per informazioni dettagliate, fare clic su **dettagli** nell'elenco a discesa nel nodo della tabella.  
  
9. Selezionare il nodo della tabella e trascinarlo sull'area del modello di elemento della seconda <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Procedura: Visualizzare i dati associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Procedura: Visualizzare dati correlati in un'applicazione Windows Forms](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)  
 [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
