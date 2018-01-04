---
title: 'Procedura: visualizzare una tavolozza dei colori con il componente ColorDialog'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- palettes [Windows Forms], showing color
- color dialog box [Windows Forms], showing color palettes
- colors [Windows Forms], allowing users to select
- color palettes [Windows Forms], dialog box
- ColorDialog component [Windows Forms], showing color palettes
- color palettes [Windows Forms], showing in ColorDialog component
- colors [Windows Forms], showing palettes
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8abaab09d2c2e20211463bb8fc93d7efaa1b38fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a>Procedura: visualizzare una tavolozza dei colori con il componente ColorDialog
Il [ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md) componente Visualizza una tavolozza di colori e restituisce una proprietà che contiene il colore in cui l'utente ha selezionato.  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a>Per scegliere un colore utilizzando il componente ColorDialog  
  
1.  Visualizzare la finestra di dialogo utilizzando il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo.  
  
2.  Utilizzare il <xref:System.Windows.Forms.DialogResult> proprietà per determinare la modalità in cui è stata chiusa la finestra di dialogo.  
  
3.  Utilizzare il <xref:System.Windows.Forms.ColorDialog.Color%2A> proprietà del <xref:System.Windows.Forms.ColorDialog> componenti su cui impostare il colore scelto.  
  
     Nell'esempio seguente, il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> gestore eventi viene aperto un <xref:System.Windows.Forms.ColorDialog> componente. Quando un colore viene scelto e l'utente fa clic su **OK**, <xref:System.Windows.Forms.Button> il colore di sfondo del controllo è impostato sul colore scelto. Nell'esempio si presuppone il modulo contiene un <xref:System.Windows.Forms.Button> controllo e un <xref:System.Windows.Forms.ColorDialog> componente.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ColorDialog>  
 [Componente ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)
