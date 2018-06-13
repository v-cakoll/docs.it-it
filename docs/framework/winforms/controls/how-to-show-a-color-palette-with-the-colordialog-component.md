---
title: 'Procedura: visualizzare una tavolozza dei colori con il componente ColorDialog'
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
ms.openlocfilehash: ea12fe19b6c8c7464f0820267face8a1d66de784
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536927"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a><span data-ttu-id="fbb46-102">Procedura: visualizzare una tavolozza dei colori con il componente ColorDialog</span><span class="sxs-lookup"><span data-stu-id="fbb46-102">How to: Show a Color Palette with the ColorDialog Component</span></span>
<span data-ttu-id="fbb46-103">Il [ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md) componente Visualizza una tavolozza di colori e restituisce una proprietà che contiene il colore in cui l'utente ha selezionato.</span><span class="sxs-lookup"><span data-stu-id="fbb46-103">The [ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md) component displays a palette of colors and returns a property containing the color the user has selected.</span></span>  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a><span data-ttu-id="fbb46-104">Per scegliere un colore utilizzando il componente ColorDialog</span><span class="sxs-lookup"><span data-stu-id="fbb46-104">To choose a color using the ColorDialog component</span></span>  
  
1.  <span data-ttu-id="fbb46-105">Visualizzare la finestra di dialogo utilizzando il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="fbb46-105">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2.  <span data-ttu-id="fbb46-106">Utilizzare il <xref:System.Windows.Forms.DialogResult> proprietà per determinare la modalità in cui è stata chiusa la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="fbb46-106">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3.  <span data-ttu-id="fbb46-107">Utilizzare il <xref:System.Windows.Forms.ColorDialog.Color%2A> proprietà del <xref:System.Windows.Forms.ColorDialog> componenti su cui impostare il colore scelto.</span><span class="sxs-lookup"><span data-stu-id="fbb46-107">Use the <xref:System.Windows.Forms.ColorDialog.Color%2A> property of the <xref:System.Windows.Forms.ColorDialog> component to set the chosen color.</span></span>  
  
     <span data-ttu-id="fbb46-108">Nell'esempio seguente, il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> gestore eventi viene aperto un <xref:System.Windows.Forms.ColorDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="fbb46-108">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="fbb46-109">Quando un colore viene scelto e l'utente fa clic su **OK**, <xref:System.Windows.Forms.Button> il colore di sfondo del controllo è impostato sul colore scelto.</span><span class="sxs-lookup"><span data-stu-id="fbb46-109">When a color is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.Button> control's background color is set to the chosen color.</span></span> <span data-ttu-id="fbb46-110">Nell'esempio si presuppone il modulo contiene un <xref:System.Windows.Forms.Button> controllo e un <xref:System.Windows.Forms.ColorDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="fbb46-110">The example assumes your form has a <xref:System.Windows.Forms.Button> control and a <xref:System.Windows.Forms.ColorDialog> component.</span></span>  
  
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
  
     <span data-ttu-id="fbb46-111">(Visual c#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="fbb46-111">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fbb46-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbb46-112">See Also</span></span>  
 <xref:System.Windows.Forms.ColorDialog>  
 [<span data-ttu-id="fbb46-113">Componente ColorDialog</span><span class="sxs-lookup"><span data-stu-id="fbb46-113">ColorDialog Component</span></span>](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)
