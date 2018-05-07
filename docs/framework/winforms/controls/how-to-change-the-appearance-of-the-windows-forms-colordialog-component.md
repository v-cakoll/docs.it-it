---
title: "Procedura: modificare l'aspetto del componente ColorDialog di Windows Form"
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
ms.openlocfilehash: 816850fa61de97b5f4c251571a74da7e0a70cba8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a>Procedura: modificare l'aspetto del componente ColorDialog di Windows Form
È possibile configurare l'aspetto di Windows Form <xref:System.Windows.Forms.ColorDialog> componente con un numero di proprietà. Nella finestra di dialogo include due sezioni, ovvero uno che mostra i colori di base e uno che consente all'utente di definire colori personalizzati.  
  
 La maggior parte delle proprietà limitare i colori, l'utente può selezionare nella finestra di dialogo. Se il <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> è impostata su `true`, l'utente è autorizzato a definire colori personalizzati. Il <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> proprietà `true` se la finestra di dialogo verrà espansa per definire colori personalizzati; in caso contrario l'utente deve fare clic su un pulsante "Definisci colori personalizzati". Quando il <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> è impostata su `true`, la finestra di dialogo consente di visualizzare tutti i colori disponibili nel set di colori di base. Se il <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> è impostata su `true`, l'utente non è possibile selezionare i colori con dithering; solo i colori a tinta unita sono disponibili per la selezione.  
  
 Se il <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> è impostata su `true`, viene visualizzato un pulsante della Guida nella finestra di dialogo. Quando l'utente fa clic sul pulsante Guida il <xref:System.Windows.Forms.ColorDialog> del componente <xref:System.Windows.Forms.CommonDialog.HelpRequest> viene generato l'evento.  
  
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
 <xref:System.Windows.Forms.ColorDialog>  
 [Componente ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)  
 [Cenni preliminari sul componente ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)
