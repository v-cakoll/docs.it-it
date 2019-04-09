---
title: 'Procedura: Raggruppare i controlli RadioButton di Windows Forms in modo che funzionino come set'
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: c785b124d0b9efdbd9a1fa85819031cad3c8857c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117897"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>Procedura: Raggruppare i controlli RadioButton di Windows Forms in modo che funzionino come set
Windows Form <xref:System.Windows.Forms.RadioButton> controlli sono progettati per consentire agli utenti una scelta tra due o più impostazioni, di cui solo uno può essere assegnato a una routine o un oggetto. Ad esempio, un gruppo di <xref:System.Windows.Forms.RadioButton> controlli che visualizzano dei vettori di pacchetto per un ordine, ma solo uno dei vettori verrà usato. Pertanto un solo <xref:System.Windows.Forms.RadioButton> alla volta può essere selezionato, anche se è una parte di un gruppo funzionale.  
  
 Gruppo di pulsanti di opzione trascinandoli all'interno di un contenitore, ad esempio un <xref:System.Windows.Forms.Panel> (controllo), un <xref:System.Windows.Forms.GroupBox> controllo o un modulo. Tutti i pulsanti di opzione che vengono aggiunti direttamente a un form costituiscono un gruppo. Per aggiungere gruppi separati, è necessario inserirli all'interno di pannelli o caselle di gruppo. Per altre informazioni sui riquadri o caselle di gruppo, vedere [Cenni preliminari sul controllo Panel](panel-control-overview-windows-forms.md) oppure [Cenni preliminari sul controllo GroupBox](groupbox-control-overview-windows-forms.md).  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>Per raggruppare controlli RadioButton come un set a funzione indipendente da altri gruppi  
  
1.  Trascinare un <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel> controllare dalle **Windows Forms** scheda il **della casella degli strumenti** nel form.  
  
2.  Disegnare <xref:System.Windows.Forms.RadioButton> ai controlli le <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel> controllo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.RadioButton>
- [Panoramica del controllo RadioButton](radiobutton-control-overview-windows-forms.md)
- [Panoramica del controllo Panel](panel-control-overview-windows-forms.md)
- [Panoramica del controllo GroupBox](groupbox-control-overview-windows-forms.md)
- [Panoramica del controllo CheckBox](checkbox-control-overview-windows-forms.md)
- [Controllo RadioButton](radiobutton-control-windows-forms.md)
