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
ms.openlocfilehash: d0a0cbbcc618e2fa52b3719bcc8f0135a1e0752e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535997"
---
# <a name="trackbar-control-overview-windows-forms"></a>Cenni preliminari sul controllo TrackBar (Windows Form)
Windows Form <xref:System.Windows.Forms.TrackBar> controllo (talvolta definito "slider") viene utilizzato per spostarsi di una grande quantità di informazioni o per visivamente un'impostazione numerica. Il <xref:System.Windows.Forms.TrackBar> controllo dispone di due parti: il cursore, noto anche come un dispositivo di scorrimento e i segni di graduazione. Il cursore è la parte che può essere modificata. La posizione corrisponde alla <xref:System.Windows.Forms.TrackBar.Value%2A> proprietà. I segni di graduazione sono indicatori visivi disposti a intervalli regolari. Controllo trackbar viene spostato ad incrementi specificati dall'utente e possono essere allineate orizzontalmente o verticalmente. Ad esempio, è possibile utilizzare l'indicatore di avanzamento per controllare il cursore intermittente o del mouse la velocità per un sistema.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Le proprietà della chiave di <xref:System.Windows.Forms.TrackBar> controllo sono <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, e <xref:System.Windows.Forms.TrackBar.Maximum%2A>. <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> è la spaziatura dei segni di graduazione. <xref:System.Windows.Forms.TrackBar.Minimum%2A> e <xref:System.Windows.Forms.TrackBar.Maximum%2A> sono i valori minimo e massimo che possono essere rappresentati sull'indicatore di avanzamento.  
  
 Altre due proprietà importanti, <xref:System.Windows.Forms.TrackBar.SmallChange%2A> e <xref:System.Windows.Forms.TrackBar.LargeChange%2A>. Il valore di <xref:System.Windows.Forms.TrackBar.SmallChange%2A> proprietà è il numero di posizioni, il cursore viene spostato in seguito al pressione dei tasti freccia sinistra o destra. Il valore di <xref:System.Windows.Forms.TrackBar.LargeChange%2A> proprietà è il numero di posizioni, il cursore viene spostato in seguito al pressione dei tasti PGSU o PGGIÙ o in risposta a mouse fa clic sull'indicatore di avanzamento su entrambi i lati del cursore.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.TrackBar>  
 [Controllo TrackBar](../../../../docs/framework/winforms/controls/trackbar-control-windows-forms.md)
