---
title: Cenni preliminari sul controllo RadioButton
ms.date: 03/30/2017
f1_keywords:
- RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
ms.openlocfilehash: bbc93046b69d39caadde4986ff56f067fc206a9e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741142"
---
# <a name="radiobutton-control-overview-windows-forms"></a>Cenni preliminari sul controllo RadioButton (Windows Form)
Windows Forms controlli <xref:System.Windows.Forms.RadioButton> presentano un set di due o più scelte che si escludono a vicenda per l'utente. Mentre i pulsanti di opzione e le caselle di controllo sembrano funzionare in modo analogo, esiste una differenza importante: quando un utente seleziona un pulsante di opzione, non è possibile selezionare anche gli altri pulsanti di opzione nello stesso gruppo. Al contrario, è possibile selezionare qualsiasi numero di caselle di controllo. La definizione di un gruppo di pulsanti di opzione indica all'utente "Ecco un set di opzioni da cui è possibile scegliere una sola e una sola".  
  
## <a name="using-the-control"></a>Uso del controllo  
 Quando si fa clic su un controllo <xref:System.Windows.Forms.RadioButton>, la relativa proprietà <xref:System.Windows.Forms.RadioButton.Checked%2A> è impostata su `true` e viene chiamato il gestore eventi <xref:System.Windows.Forms.Control.Click>. L'evento <xref:System.Windows.Forms.RadioButton.CheckedChanged> viene generato quando cambia il valore della proprietà <xref:System.Windows.Forms.RadioButton.Checked%2A>. Se la proprietà <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> è impostata su `true` (impostazione predefinita), quando si seleziona il pulsante di opzione tutti gli altri elementi del gruppo vengono cancellati automaticamente. Questa proprietà viene in genere impostata su `false` solo quando viene usato il codice di convalida per verificare che il pulsante di opzione selezionato sia un'opzione consentita. Il testo visualizzato all'interno del controllo viene impostato con la proprietà <xref:System.Windows.Forms.Control.Text%2A>, che può contenere tasti di scelta rapida. Una chiave di accesso consente a un utente di fare clic sul controllo premendo il tasto ALT con il tasto di accesso. Per altre informazioni, vedere [procedura: creare chiavi di accesso per controlli Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md) e [procedura: impostare il testo visualizzato da un controllo Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 Il controllo <xref:System.Windows.Forms.RadioButton> può apparire come un pulsante di comando, che sembra essere stato premuto se selezionato, se la proprietà <xref:System.Windows.Forms.RadioButton.Appearance%2A> è impostata su <xref:System.Windows.Forms.Appearance.Button>. I pulsanti di opzione possono anche visualizzare immagini usando le proprietà <xref:System.Windows.Forms.ButtonBase.Image%2A> e <xref:System.Windows.Forms.ButtonBase.ImageList%2A>. Per altre informazioni, vedere [procedura: impostare l'immagine visualizzata da un controllo Windows Forms](how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.RadioButton>
- [Panoramica sul controllo Panel](panel-control-overview-windows-forms.md)
- [Panoramica sul controllo GroupBox](groupbox-control-overview-windows-forms.md)
- [Panoramica sul controllo CheckBox](checkbox-control-overview-windows-forms.md)
- [Procedura: Creare tasti di scelta per i controlli Windows Form](how-to-create-access-keys-for-windows-forms-controls.md)
- [Procedura: Impostare il testo visualizzato da un controllo Windows Form](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Procedura: Raggruppare controlli RadioButton Windows Form in modo che funzionino come set](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)
- [Controllo RadioButton](radiobutton-control-windows-forms.md)
