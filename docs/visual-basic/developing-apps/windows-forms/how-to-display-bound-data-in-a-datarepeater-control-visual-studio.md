---
title: 'Procedura: visualizzare i dati associati in un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
ms.openlocfilehash: b96fb33a0dcf80a86d1fcb6e219e5f35b1f7351c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589867"
---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a>Procedura: visualizzare i dati associati in un controllo DataRepeater (Visual Studio)
L'utilizzo più comune del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo consiste nel visualizzare i dati associati da un database o un'altra origine dati.  
  
 Oltre a controlli con associazione, si desidera aggiungere altri controlli, ad esempio un'etichetta statica o di un'immagine che viene ripetuta in ogni elemento di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Per ulteriori informazioni, vedere [procedura: visualizzare i controlli non associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
 È anche possibile associare a un'origine dati in fase di esecuzione impostando la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> proprietà `True` e l'assegnazione di un'origine dati per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> proprietà. In questo caso, è necessario gestire tutte le interazioni con l'origine dati. Per ulteriori informazioni, vedere [modalità virtuale nel controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a>Per creare un oggetto con associazione a dati DataRepeater  
  
1.  Trascinare un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo il **Visual Basic Power Packs** nella scheda il **della casella degli strumenti** a un controllo form o del contenitore.  
  
2.  Trascinare i quadratini di ridimensionamento e la posizione per dimensioni e posizione del controllo.  
  
     Si noti che il controllo dispone di due aree rettangolari. L'area superiore è il *modello di elemento*; i controlli aggiunti al modello verranno ripetuti in ogni voce di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo in fase di esecuzione. L'area inferiore è la *viewport*, in cui verranno visualizzati gli elementi.  
  
     È possibile ridimensionare e posizionare il controllo o il modello di elemento tramite la modifica anche il **dimensioni** e **posizione** proprietà nella finestra Proprietà.  
  
3.  Scegliere **Mostra origini dati** dal menu **Dati**.  
  
    > [!NOTE]
    >  Se il **origini dati** finestra è vuota, aggiungere un'origine dati. Per altre informazioni, vedere [Add new data sources](/visualstudio/data-tools/add-new-data-sources) (Aggiungere nuove origini dati).  
  
4.  Nel **origini dati** finestra, selezionare il nodo di livello superiore per la tabella che contiene i dati che si desidera associare.  
  
5.  Modificare il tipo di rilascio della tabella da `Details` facendo `Details` nell'elenco a discesa nel nodo della tabella.  
  
6.  Selezionare il nodo della tabella e trascinarlo sull'area del modello di elemento del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
     È possibile specificare i tipi di controlli che vengono visualizzati per ogni campo. Per ulteriori informazioni, vedere [impostare il controllo da creare durante il trascinamento dalla finestra Origini dati](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Procedura: Visualizzare i controlli non associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [Procedura: creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
