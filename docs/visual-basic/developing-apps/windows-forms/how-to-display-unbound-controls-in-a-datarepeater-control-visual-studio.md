---
title: 'Procedura: visualizzare i controlli non associati in un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
ms.openlocfilehash: 698e518a4ed10ed6cf14ccafc6833b1acf8752db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588106"
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a>Procedura: visualizzare i controlli non associati in un controllo DataRepeater (Visual Studio)
Oltre a controlli con associazione, si desidera aggiungere altri controlli a un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, ad esempio un'etichetta statica o di un'immagine che viene ripetuta in ogni elemento di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
> [!NOTE]
>  È inoltre necessario disporre almeno di un controllo associato <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> o verrà visualizzato nulla in fase di esecuzione.  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a>Per aggiungere i controlli non associati a un controllo DataRepeater  
  
1.  Trascinare un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo il **Visual Basic Power Packs** nella scheda il **della casella degli strumenti** a un controllo form o del contenitore.  
  
2.  Trascinare i quadratini di ridimensionamento e la posizione per dimensioni e posizione del controllo.  
  
     È anche possibile ridimensionare e posizionare il controllo modificando il **dimensioni** e **posizione** proprietà nella finestra Proprietà.  
  
3.  Aggiungere almeno un controllo con associazione a dati per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Per ulteriori informazioni, vedere [procedura: visualizzare i dati associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
4.  Trascinare un controllo dal **della casella degli strumenti** all'area del modello di elemento del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
     Si noti che il controllo dispone di due aree rettangolari. L'area interna è il *modello di elemento*; i controlli aggiunti al modello verranno ripetuti in ogni voce di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo in fase di esecuzione. L'area esterna è di *viewport*, in cui verranno visualizzati gli elementi; i controlli che vengono aggiunti a questa area non verranno visualizzati in fase di esecuzione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [Procedura: Visualizzare i dati associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Procedura: creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
