---
title: Cenni preliminari sul controllo RadioButton (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
ms.openlocfilehash: 1210658226d9bcacbf4904fdc90a9908c34f5b73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755948"
---
# <a name="radiobutton-control-overview-windows-forms"></a>Cenni preliminari sul controllo RadioButton (Windows Form)
Windows Form <xref:System.Windows.Forms.RadioButton> controlli presentano un insieme di due o più opzioni si escludono a vicenda all'utente. Anche se i pulsanti di opzione e caselle di controllo sembra funzionare allo stesso modo, è un'importante differenza: quando un utente seleziona un pulsante di opzione, non è possibile selezionare anche gli altri pulsanti di opzione nello stesso gruppo. Al contrario, è possibile selezionare un numero qualsiasi delle caselle di controllo. La definizione di un gruppo di pulsanti di opzione indica all'utente, "Di seguito è un set di opzioni da cui è possibile scegliere solo uno".  
  
## <a name="using-the-control"></a>Utilizzo del controllo  
 Quando un <xref:System.Windows.Forms.RadioButton> controllo viene selezionato, relativo <xref:System.Windows.Forms.RadioButton.Checked%2A> è impostata su `true` e il <xref:System.Windows.Forms.Control.Click> gestore eventi viene chiamato. Il <xref:System.Windows.Forms.RadioButton.CheckedChanged> evento viene generato quando il valore della <xref:System.Windows.Forms.RadioButton.Checked%2A> le modifiche alle proprietà. Se il <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> è impostata su `true` (impostazione predefinita), quando viene selezionato il pulsante di opzione tutti gli altri del gruppo vengono automaticamente cancellati. Questa proprietà viene in genere impostata solo su `false` quando si usa codice di convalida per assicurarsi che il pulsante di opzione selezionato è un'opzione disponibile. Il testo visualizzato all'interno del controllo è impostato con il <xref:System.Windows.Forms.Control.Text%2A> proprietà, che può contenere i tasti di scelta rapida. Una chiave di accesso consente all'utente di "fare clic su" controllo premendo il tasto ALT con la chiave di accesso. Per altre informazioni, vedere [Procedura: Creare le chiavi di accesso per i controlli di Windows Form](how-to-create-access-keys-for-windows-forms-controls.md) e [come: Impostare il testo visualizzato dal controllo di un Windows Form](how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 Il <xref:System.Windows.Forms.RadioButton> controllo viene visualizzato come un pulsante di comando, viene visualizzato sia stato attivato se è selezionata, se il <xref:System.Windows.Forms.RadioButton.Appearance%2A> è impostata su <xref:System.Windows.Forms.Appearance.Button>. Pulsanti di opzione possono anche visualizzare immagini usando il <xref:System.Windows.Forms.ButtonBase.Image%2A> e <xref:System.Windows.Forms.ButtonBase.ImageList%2A> proprietà. Per altre informazioni, vedere [Procedura: Impostare l'immagine visualizzata da controllo di un Windows Form](how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.RadioButton>
- [Panoramica sul controllo Panel](panel-control-overview-windows-forms.md)
- [Panoramica sul controllo GroupBox](groupbox-control-overview-windows-forms.md)
- [Panoramica sul controllo CheckBox](checkbox-control-overview-windows-forms.md)
- [Procedura: Creare le chiavi di accesso per i controlli Windows Form](how-to-create-access-keys-for-windows-forms-controls.md)
- [Procedura: Impostare il testo visualizzato dal controllo di un Windows Form](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Procedura: Gruppo Windows Form controlli RadioButton funzionino come Set](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)
- [Controllo RadioButton](radiobutton-control-windows-forms.md)
