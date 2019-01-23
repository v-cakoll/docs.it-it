---
title: Cenni preliminari sul componente ColorDialog (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 9ef7d667b582d3b227f0f0e8af5e7e0335cd4860
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570109"
---
# <a name="colordialog-component-overview-windows-forms"></a>Cenni preliminari sul componente ColorDialog (Windows Form)
I moduli di Windows <xref:System.Windows.Forms.ColorDialog> componente è una finestra di dialogo preconfigurata che consente all'utente di selezionare un colore dalla tavolozza e di aggiungere colori personalizzati alla tavolozza. È la stessa finestra di dialogo visualizzata in altre applicazioni basate su Windows per selezionare i colori. e costituisce una semplice soluzione, utilizzabile nell'applicazione basata su Windows creata, per evitare di configurare una propria finestra di dialogo.  
  
 Il colore selezionato nella finestra di dialogo viene restituito nel <xref:System.Windows.Forms.ColorDialog.Color%2A> proprietà. Se il <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> è impostata su `false`, il pulsante "Definisci colori personalizzati" è disabilitato e l'utente è limitato per i colori predefiniti della tavolozza. Se il <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> è impostata su `true`, l'utente non è possibile selezionare i colori con dithering. Per visualizzare la finestra di dialogo, è necessario chiamare il relativo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> (metodo).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.ColorDialog>
- [Componente ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)
- [Controlli e componenti della finestra di dialogo](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
- [Procedura: Modificare l'aspetto del componente ColorDialog di Windows Form](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
