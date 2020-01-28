---
title: Modificare l'aspetto del componente ColorDialog
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
ms.openlocfilehash: 0402d7f3c03a0771512a03ac54e1b093c9fe6e9b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746643"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a>Procedura: modificare l'aspetto del componente ColorDialog di Windows Form
È possibile configurare l'aspetto del componente Windows Forms <xref:System.Windows.Forms.ColorDialog> con una serie di proprietà. La finestra di dialogo include due sezioni, una che mostra i colori di base e l'altra che consente all'utente di definire colori personalizzati.  
  
 La maggior parte delle proprietà consente di limitare i colori selezionabili dall'utente dalla finestra di dialogo. Se la proprietà <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> è impostata su `true`, l'utente può definire colori personalizzati. La proprietà <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> viene `true` se la finestra di dialogo è espansa per definire colori personalizzati; in caso contrario, l'utente deve fare clic sul pulsante "Definisci colori personalizzati". Quando la proprietà <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> è impostata su `true`, nella finestra di dialogo vengono visualizzati tutti i colori disponibili nel set di colori di base. Se la proprietà <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> è impostata su `true`, l'utente non è in grado di selezionare i colori dimessi; per la selezione sono disponibili solo colori a tinta unita.  
  
 Se la proprietà <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> è impostata su `true`, nella finestra di dialogo viene visualizzato un pulsante?. Quando l'utente fa clic sul pulsante?, viene generato l'evento <xref:System.Windows.Forms.CommonDialog.HelpRequest> del componente <xref:System.Windows.Forms.ColorDialog>.  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a>Per configurare l'aspetto della finestra di dialogo colore  
  
1. Impostare le proprietà <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>e <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> sui valori desiderati.  
  
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
- [Cenni preliminari sul componente ColorDialog](colordialog-component-overview-windows-forms.md)
