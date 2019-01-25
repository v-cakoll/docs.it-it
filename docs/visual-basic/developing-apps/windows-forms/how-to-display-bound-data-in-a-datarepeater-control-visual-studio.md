---
title: 'Procedura: Visualizzare i dati associati in un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
ms.openlocfilehash: dbcd814edb78c54ce5629a1a8761142674fe6135
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684619"
---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a>Procedura: Visualizzare i dati associati in un controllo DataRepeater (Visual Studio)
L'uso più comune del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo consiste nel visualizzare i dati associati da un database o un'altra origine dati.  
  
 Oltre ai controlli associati, è possibile aggiungere altri controlli, ad esempio un'etichetta statica o di un'immagine che viene ripetuta per ogni elemento nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Per altre informazioni, vedere [Procedura: Visualizzare non associati a controlli in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
 È anche possibile associare a un'origine dati in fase di esecuzione, impostando il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> proprietà `True` e l'assegnazione di un'origine dati per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> proprietà. In questo caso, è necessario gestire tutte le interazioni con l'origine dati. Per altre informazioni, vedere [modalità virtuale nel controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a>Per creare un oggetto con associazione a dati DataRepeater  
  
1.  Trascinare un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllare dal **Visual Basic Power Packs** scheda il **casella degli strumenti** a un form o un controllo contenitore.  
  
2.  Trascinare i quadratini di ridimensionamento e la posizione per le dimensioni e posizionare il controllo.  
  
     Si noti che il controllo dispone di due aree rettangolari. L'area superiore è il *modello di elemento*; i controlli aggiunti al modello verranno ripetuti in ogni elemento nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo in fase di esecuzione. L'area inferiore è il *viewport*, in cui verranno visualizzati gli elementi.  
  
     È anche possibile ridimensionare e posizionare il controllo o il modello di elemento modificando la **dimensioni** e **posizione** proprietà nella finestra Proprietà.  
  
3.  Scegliere **Mostra origini dati** dal menu **Dati**.  
  
    > [!NOTE]
    >  Se il **Zdroje dat** finestra è vuota, aggiungere un'origine dati a esso. Per altre informazioni, vedere [Add new data sources](/visualstudio/data-tools/add-new-data-sources) (Aggiungere nuove origini dati).  
  
4.  Nel **Zdroje dat** finestra, selezionare il nodo di primo livello per la tabella che contiene i dati che si desidera associare.  
  
5.  Modificare il tipo di rilascio della tabella `Details` facendo clic `Details` nell'elenco a discesa nel nodo della tabella.  
  
6.  Selezionare il nodo della tabella e trascinarlo nell'area modello dell'elemento di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
     È possibile specificare tipi di controlli che vengono visualizzati per ogni campo. Per altre informazioni, vedere [impostare il controllo da creare durante il trascinamento dalla finestra Origini dei dati](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Procedura: Visualizzare i controlli non associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)
- [Procedura: Creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
- [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
