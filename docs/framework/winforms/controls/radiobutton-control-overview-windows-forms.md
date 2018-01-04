---
title: Cenni preliminari sul controllo RadioButton (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 67befd973dec38628f97a0d3153c399d48c18305
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="radiobutton-control-overview-windows-forms"></a>Cenni preliminari sul controllo RadioButton (Windows Form)
Windows Form <xref:System.Windows.Forms.RadioButton> controlli presentano all'utente un set di due o più opzioni si escludono a vicenda. Mentre i pulsanti di opzione e caselle di controllo sembra funzionare in modo analogo, sussiste una differenza importante: quando un utente seleziona un pulsante di opzione, non è possibile selezionare anche altri pulsanti di opzione nello stesso gruppo. Al contrario, è possibile selezionare un numero qualsiasi di caselle di controllo. Definizione di un gruppo di pulsanti di opzione indica all'utente, "Di seguito è un insieme di opzioni da cui è possibile scegliere una sola".  
  
## <a name="using-the-control"></a>Utilizzo del controllo  
 Quando un <xref:System.Windows.Forms.RadioButton> si fa clic sul controllo, il relativo <xref:System.Windows.Forms.RadioButton.Checked%2A> è impostata su `true` e <xref:System.Windows.Forms.Control.Click> gestore eventi viene chiamato. Il <xref:System.Windows.Forms.RadioButton.CheckedChanged> evento viene generato quando il valore della <xref:System.Windows.Forms.RadioButton.Checked%2A> le modifiche alle proprietà. Se il <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> è impostata su `true` (impostazione predefinita), quando si seleziona il pulsante di opzione tutti gli altri utenti nel gruppo vengono automaticamente deselezionati. Questa proprietà viene in genere impostato solo su `false` quando il codice di convalida viene utilizzato per verificare che il pulsante di opzione selezionato sia un'opzione disponibile. Il testo visualizzato all'interno del controllo viene impostato con la <xref:System.Windows.Forms.Control.Text%2A> proprietà, che può contenere i tasti di scelta rapida. Una chiave di accesso consente all'utente di "fare clic su" controllo premendo il tasto ALT con la chiave di accesso. Per ulteriori informazioni, vedere [procedura: creazione di chiavi per i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) e [procedura: impostare il testo visualizzato da un controllo Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 Il <xref:System.Windows.Forms.RadioButton> controllo viene visualizzato come un pulsante di comando, viene visualizzata sia stato attivato se è selezionata, se il <xref:System.Windows.Forms.RadioButton.Appearance%2A> è impostata su <xref:System.Windows.Forms.Appearance.Button>. Pulsanti di opzione possono inoltre visualizzare immagini utilizzando la <xref:System.Windows.Forms.ButtonBase.Image%2A> e <xref:System.Windows.Forms.ButtonBase.ImageList%2A> proprietà. Per ulteriori informazioni, vedere [procedura: impostare l'immagine visualizzata da un controllo Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.RadioButton>  
 [Panoramica sul controllo Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Panoramica sul controllo GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [Panoramica sul controllo CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [Procedura: Creare tasti di scelta per i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [Procedura: Impostare il testo visualizzato da un controllo Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Procedura: Raggruppare controlli RadioButton Windows Form in modo che funzionino come set](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)  
 [Controllo RadioButton](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
