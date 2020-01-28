---
title: Raggruppare i controlli RadioButton per funzionare come set
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: c4b37c84bf0f93837b91c743c7681d39fd83a659
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732946"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>Procedura: raggruppare controlli RadioButton Windows Form in modo che funzionino come set
Windows Forms controlli <xref:System.Windows.Forms.RadioButton> sono progettati per fornire agli utenti una scelta tra due o più impostazioni, di cui solo una può essere assegnata a una procedura o a un oggetto. Ad esempio, un gruppo di controlli di <xref:System.Windows.Forms.RadioButton> può visualizzare una scelta di gestori di pacchetti per un ordine, ma solo uno dei vettori verrà usato. È pertanto possibile selezionare un solo <xref:System.Windows.Forms.RadioButton> alla volta, anche se fa parte di un gruppo funzionale.  
  
 Per raggruppare i pulsanti di opzione, è possibile disegnarli all'interno di un contenitore, ad esempio un controllo <xref:System.Windows.Forms.Panel>, un controllo <xref:System.Windows.Forms.GroupBox> o un form. Tutti i pulsanti di opzione aggiunti direttamente a un modulo diventano un gruppo. Per aggiungere gruppi distinti, è necessario inserirli nei pannelli o nelle caselle di gruppo. Per ulteriori informazioni sui pannelli o sulle caselle di gruppo, vedere [Cenni preliminari sul controllo Panel](panel-control-overview-windows-forms.md) o [Cenni preliminari sul controllo GroupBox](groupbox-control-overview-windows-forms.md).  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>Per raggruppare i controlli RadioButton come set per funzionare indipendentemente da altri set  
  
1. Trascinare un controllo <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel> dalla scheda **Windows Forms** della **casella degli strumenti** nel form.  
  
2. Consente di creare <xref:System.Windows.Forms.RadioButton> controlli sul controllo <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.RadioButton>
- [Panoramica sul controllo RadioButton](radiobutton-control-overview-windows-forms.md)
- [Panoramica sul controllo Panel](panel-control-overview-windows-forms.md)
- [Panoramica sul controllo GroupBox](groupbox-control-overview-windows-forms.md)
- [Panoramica sul controllo CheckBox](checkbox-control-overview-windows-forms.md)
- [Controllo RadioButton](radiobutton-control-windows-forms.md)
