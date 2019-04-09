---
title: "Procedura: Modificare l'aspetto del componente ColorDialog di Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: d79139ac3d11d3cd9a7d1bbe1f12e14df83530e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094645"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a>Procedura: Modificare l'aspetto del componente ColorDialog di Windows Forms
È possibile configurare l'aspetto delle forme Windows <xref:System.Windows.Forms.ColorDialog> componente con un numero di proprietà. La finestra di dialogo include due sezioni, ovvero uno che mostra i colori di base e uno che consente all'utente di definire colori personalizzati.  
  
 La maggior parte delle proprietà limitare colori selezionabili dall'utente nella finestra di dialogo. Se il <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> è impostata su `true`, l'utente può definire colori personalizzati. Il <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> è di proprietà `true` se la finestra di dialogo viene espanso per definire colori personalizzati; in caso contrario, l'utente deve fare clic su un pulsante "Definisci colori personalizzati". Quando la <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> è impostata su `true`, la finestra di dialogo consente di visualizzare tutti i colori disponibili nel set di colori di base. Se il <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> è impostata su `true`, l'utente non è possibile selezionare i colori con dithering; sono possibile selezionare solo colori a tinta unita.  
  
 Se il <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> è impostata su `true`, viene visualizzato un pulsante nella finestra di dialogo. Quando l'utente fa clic sul pulsante della Guida, il <xref:System.Windows.Forms.ColorDialog> del componente <xref:System.Windows.Forms.CommonDialog.HelpRequest> viene generato l'evento.  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a>Per configurare l'aspetto della finestra di dialogo colore  
  
1.  Impostare il <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, e <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> proprietà sui valori desiderati.  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ColorDialog>
- [Componente ColorDialog](colordialog-component-windows-forms.md)
- [Panoramica del componente ColorDialog](colordialog-component-overview-windows-forms.md)
