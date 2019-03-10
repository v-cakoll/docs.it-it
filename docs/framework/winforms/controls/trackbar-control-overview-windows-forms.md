---
title: Cenni preliminari sul controllo TrackBar (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
ms.openlocfilehash: 74a8feba14b7e2186fb64729cb915e53132805d5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707014"
---
# <a name="trackbar-control-overview-windows-forms"></a>Cenni preliminari sul controllo TrackBar (Windows Form)
I moduli di Windows <xref:System.Windows.Forms.TrackBar> controllo (talvolta definito "slider") viene usato per spostarsi all'interno di una grande quantità di informazioni o per regolare visivamente un'impostazione numerica. Il <xref:System.Windows.Forms.TrackBar> controllo è costituito da due parti: il controllo thumb, noto anche come un dispositivo di scorrimento e i segni di graduazione. Il controllo thumb è la parte che può essere modificata. La posizione corrisponde alla <xref:System.Windows.Forms.TrackBar.Value%2A> proprietà. I segni di graduazione sono indicatori visivi che sono disposti a intervalli regolari. Consente di spostare l'indicatore di avanzamento in base a incrementi specificati e possono essere allineate orizzontalmente o verticalmente. Ad esempio, è possibile utilizzare l'indicatore di avanzamento per il cursore per il lampeggiamento mouse o frequenza velocità per un sistema di controllo.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Le proprietà chiave del <xref:System.Windows.Forms.TrackBar> controllo vengono <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, e <xref:System.Windows.Forms.TrackBar.Maximum%2A>. <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> è la spaziatura dei segni di graduazione. <xref:System.Windows.Forms.TrackBar.Minimum%2A> e <xref:System.Windows.Forms.TrackBar.Maximum%2A> sono i valori minimo e massimo che possono essere rappresentati sull'indicatore di avanzamento.  
  
 Altre due importanti proprietà sono <xref:System.Windows.Forms.TrackBar.SmallChange%2A> e <xref:System.Windows.Forms.TrackBar.LargeChange%2A>. Il valore della <xref:System.Windows.Forms.TrackBar.SmallChange%2A> proprietà è il numero di posizioni il cursore viene spostato in seguito alla pressione dei tasti freccia sinistra o destra. Il valore della <xref:System.Windows.Forms.TrackBar.LargeChange%2A> proprietà è il numero di posizioni il cursore viene spostato in seguito alla pressione dei tasti PGSU o PGGIÙ o in risposta al mouse fa clic sull'indicatore di avanzamento in entrambi i lati del cursore.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.TrackBar>
- [Controllo TrackBar](trackbar-control-windows-forms.md)
