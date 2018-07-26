---
title: 'Procedura: creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
ms.openlocfilehash: 84639a5d49a3fa4a8c6845793c39fc8a67c31e02
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245536"
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a>Procedura: creare un form Master-Details mediante due controlli DataRepeater (Visual Studio)
È possibile visualizzare i dati correlati usando due o più <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controlli per creare un form master-details. Potrebbe ad esempio, si desidera visualizzare un elenco di clienti in uno <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>e quando l'utente seleziona un cliente, è possibile visualizzare un elenco di ordini del cliente in un secondo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
 È possibile visualizzare i dati correlati trascinando gli elementi di dettaglio che condividono lo stesso nodo di tabella master dal **Zdroje dat** finestra in un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Ad esempio, se si dispone di un'origine dati che dispone di una tabella Customers e una tabella di ordini correlata, vedrai entrambe le tabelle come nodi di primo livello nella visualizzazione struttura ad albero di **Zdroje dat** finestra. Espandere il nodo di clienti in modo che è possibile visualizzare le colonne. Si noti che l'ultima colonna nell'elenco è un nodo che rappresenta la tabella Orders. Questo nodo rappresenta gli ordini correlati per un cliente.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a>Per visualizzare i dati correlati in due controlli DataRepeater  
  
1.  Trascinare due <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> dei controlli il **Visual Basic Power Packs** scheda il **casella degli strumenti** a un form o un controllo contenitore.  
  
2.  Trascinare i quadratini di ridimensionamento e la posizione per le dimensioni dei controlli e il posizionarli side-by-side.  
  
3.  Scegliere **Mostra origini dati** dal menu **Dati**.  
  
    > [!NOTE]
    >  Se il **Zdroje dat** finestra è vuota, aggiungere un'origine dati a esso. Per altre informazioni, vedere [Add new data sources](/visualstudio/data-tools/add-new-data-sources) (Aggiungere nuove origini dati).  
  
4.  Nel **Zdroje dat** finestra, selezionare il nodo di primo livello per la tabella master.  
  
5.  Modificare il tipo di rilascio della tabella master ai dettagli facendo **dettagli** nell'elenco a discesa nel nodo della tabella.  
  
6.  Trascinare il nodo della tabella master nell'area modello dell'elemento del primo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
7.  Espandere il nodo di tabella master e selezionare il nodo dettaglio della tabella correlata.  
  
8.  Modificare il tipo di rilascio della tabella dettagli per informazioni dettagliate facendo **dettagli** nell'elenco a discesa nel nodo della tabella.  
  
9. Selezionare il nodo della tabella e trascinarlo nell'area modello dell'elemento del secondo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Procedura: Visualizzare i dati associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Procedura: Visualizzare dati correlati in un'applicazione Windows Forms](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
