---
title: Raggruppare i controlli RadioButton per funzionare come set
description: Informazioni su come raggruppare Windows Forms controlli RadioButton per funzionare in modo indipendente da altri set.
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: 9f6795330922e739cca1f2b5c11bb2ec68bb4e84
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325926"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>Procedura: raggruppare controlli RadioButton Windows Form in modo che funzionino come set
Windows Forms <xref:System.Windows.Forms.RadioButton> controlli sono progettati per fornire agli utenti una scelta tra due o più impostazioni, di cui solo una può essere assegnata a una procedura o a un oggetto. Un gruppo di controlli, ad esempio, <xref:System.Windows.Forms.RadioButton> può visualizzare una scelta di gestori di pacchetti per un ordine, ma solo uno dei vettori verrà usato. È pertanto <xref:System.Windows.Forms.RadioButton> possibile selezionare solo uno alla volta, anche se fa parte di un gruppo funzionale.  
  
 Per raggruppare i pulsanti di opzione, è possibile disegnarli all'interno di un contenitore, ad esempio un <xref:System.Windows.Forms.Panel> controllo, un <xref:System.Windows.Forms.GroupBox> controllo o un form. Tutti i pulsanti di opzione aggiunti direttamente a un modulo diventano un gruppo. Per aggiungere gruppi distinti, è necessario inserirli nei pannelli o nelle caselle di gruppo. Per ulteriori informazioni sui pannelli o sulle caselle di gruppo, vedere [Cenni preliminari sul controllo Panel](panel-control-overview-windows-forms.md) o [Cenni preliminari sul controllo GroupBox](groupbox-control-overview-windows-forms.md).  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>Per raggruppare i controlli RadioButton come set per funzionare indipendentemente da altri set  
  
1. Trascinare un <xref:System.Windows.Forms.GroupBox> <xref:System.Windows.Forms.Panel> controllo o dalla scheda **Windows Forms** della **casella degli strumenti** nel form.  
  
2. Consente <xref:System.Windows.Forms.RadioButton> di creare controlli <xref:System.Windows.Forms.GroupBox> sul <xref:System.Windows.Forms.Panel> controllo o.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Windows.Forms.RadioButton>
- [Cenni preliminari sul controllo RadioButton](radiobutton-control-overview-windows-forms.md)
- [Panoramica del controllo Panel](panel-control-overview-windows-forms.md)
- [Cenni preliminari sul controllo GroupBox](groupbox-control-overview-windows-forms.md)
- [Panoramica del controllo CheckBox](checkbox-control-overview-windows-forms.md)
- [Controllo RadioButton](radiobutton-control-windows-forms.md)
