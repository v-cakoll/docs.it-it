---
title: Panoramica del componente ColorDialog
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 48d9d5072335908f85e65933dadafb1b69f28528
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736972"
---
# <a name="colordialog-component-overview-windows-forms"></a>Cenni preliminari sul componente ColorDialog (Windows Form)
Il componente Windows Forms <xref:System.Windows.Forms.ColorDialog> è una finestra di dialogo preconfigurata che consente all'utente di selezionare un colore da una tavolozza e di aggiungere colori personalizzati alla tavolozza. È la stessa finestra di dialogo visualizzata in altre applicazioni basate su Windows per selezionare i colori. e costituisce una semplice soluzione, utilizzabile nell'applicazione basata su Windows creata, per evitare di configurare una propria finestra di dialogo.  
  
 Il colore selezionato nella finestra di dialogo viene restituito nella proprietà <xref:System.Windows.Forms.ColorDialog.Color%2A>. Se la proprietà <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> è impostata su `false`, il pulsante "Definisci colori personalizzati" è disabilitato e l'utente è limitato ai colori predefiniti della tavolozza. Se la proprietà <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> è impostata su `true`, l'utente non sarà in grado di selezionare i colori dimessi. Per visualizzare la finestra di dialogo, è necessario chiamare il relativo metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ColorDialog>
- [Componente ColorDialog](colordialog-component-windows-forms.md)
- [Controlli e componenti della finestra di dialogo](dialog-box-controls-and-components-windows-forms.md)
- [Procedura: Modificare l'aspetto del componente ColorDialog di Windows Form](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
