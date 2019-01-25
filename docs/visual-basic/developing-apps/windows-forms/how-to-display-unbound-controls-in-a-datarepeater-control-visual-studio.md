---
title: 'Procedura: Visualizzare i controlli non associati in un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
ms.openlocfilehash: a20e1ba83d1963bc3d4c135817767ee02fcbdeda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730789"
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a>Procedura: Visualizzare i controlli non associati in un controllo DataRepeater (Visual Studio)
Oltre ai controlli associati, è possibile aggiungere altri controlli a un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, ad esempio un'etichetta statica o di un'immagine che viene ripetuta in ogni elemento di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
> [!NOTE]
>  È anche necessario almeno un controllo associato <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> o non verrà visualizzata in fase di esecuzione.  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a>Per aggiungere i controlli non associati a un controllo DataRepeater  
  
1.  Trascinare un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllare dal **Visual Basic Power Packs** scheda il **casella degli strumenti** a un form o un controllo contenitore.  
  
2.  Trascinare i quadratini di ridimensionamento e la posizione per le dimensioni e posizionare il controllo.  
  
     È anche possibile ridimensionare e posizionare il controllo modificando la **dimensioni** e **posizione** proprietà nella finestra Proprietà.  
  
3.  Aggiungere almeno un controllo con associazione a dati per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Per altre informazioni, vedere [Procedura: Visualizzare i dati associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
4.  Trascinare un controllo dal **casella degli strumenti** nell'area modello dell'elemento del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
     Si noti che il controllo dispone di due aree rettangolari. L'area interna è il *modello di elemento*; i controlli aggiunti al modello verranno ripetuti in ciascun elemento di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo in fase di esecuzione. L'area esterna è il *viewport*, in cui gli elementi verranno visualizzati; controlli che vengono aggiunti a questa area non verranno visualizzati in fase di esecuzione.  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [Procedura: Visualizzare i dati associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [Procedura: Creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
- [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
