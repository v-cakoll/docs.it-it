---
title: 'Procedura: Visualizzare una tavolozza dei colori con il componente ColorDialog'
ms.date: 03/30/2017
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
ms.openlocfilehash: 587b2c3a502ec8a1cb2f4f7c0d981baa0f18ead6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298019"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a>Procedura: Visualizzare una tavolozza dei colori con il componente ColorDialog
Il [ColorDialog](colordialog-component-windows-forms.md) componente Visualizza una tavolozza di colori e restituisce una proprietà che contiene il colore selezionato dall'utente.  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a>Per scegliere un colore con il componente ColorDialog  
  
1. Visualizzare la finestra di dialogo tramite il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> (metodo).  
  
2. Usare il <xref:System.Windows.Forms.DialogResult> proprietà per determinare come è stata chiusa la finestra di dialogo.  
  
3. Usare la <xref:System.Windows.Forms.ColorDialog.Color%2A> proprietà del <xref:System.Windows.Forms.ColorDialog> componenti su cui impostare il colore scelto.  
  
     Nell'esempio seguente, il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> gestore eventi apre un <xref:System.Windows.Forms.ColorDialog> componente. Quando un colore è selezionata e l'utente sceglie **OK**, il <xref:System.Windows.Forms.Button> colore di sfondo del controllo è impostato sul colore scelto. L'esempio presuppone che il form contenga un <xref:System.Windows.Forms.Button> controllo e un <xref:System.Windows.Forms.ColorDialog> componente.  
  
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
  
     (Visual c#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ColorDialog>
- [Componente ColorDialog](colordialog-component-windows-forms.md)
