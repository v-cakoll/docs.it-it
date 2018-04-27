---
title: 'Procedura: visualizzare un elenco di tipi di carattere con il componente FontDialog'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7b8efd576ac33005694ae11ea0530f86673ee858
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a><span data-ttu-id="05ea4-102">Procedura: visualizzare un elenco di tipi di carattere con il componente FontDialog</span><span class="sxs-lookup"><span data-stu-id="05ea4-102">How to: Show a Font List with the FontDialog Component</span></span>
<span data-ttu-id="05ea4-103">Il [FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) componente consente agli utenti di selezionare un tipo di carattere, nonché modificarne la visualizzazione, ad esempio lo spessore e dimensioni.</span><span class="sxs-lookup"><span data-stu-id="05ea4-103">The [FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) component allows users to select a font, as well as change its display aspects, such as its weight and size.</span></span>  
  
 <span data-ttu-id="05ea4-104">Il tipo di carattere selezionato nella finestra di dialogo viene restituito nel <xref:System.Windows.Forms.FontDialog.Font%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="05ea4-104">The font selected in the dialog box is returned in the <xref:System.Windows.Forms.FontDialog.Font%2A> property.</span></span> <span data-ttu-id="05ea4-105">Pertanto, sfruttare i vantaggi del tipo di carattere selezionato dall'utente è semplice come leggere una proprietà.</span><span class="sxs-lookup"><span data-stu-id="05ea4-105">Thus, taking advantage of the font selected by the user is as easy as reading a property.</span></span>  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a><span data-ttu-id="05ea4-106">Per selezionare le proprietà di tipo di carattere utilizzando il componente FontDialog</span><span class="sxs-lookup"><span data-stu-id="05ea4-106">To select font properties using the FontDialog Component</span></span>  
  
1.  <span data-ttu-id="05ea4-107">Visualizzare la finestra di dialogo utilizzando il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="05ea4-107">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2.  <span data-ttu-id="05ea4-108">Utilizzare il <xref:System.Windows.Forms.DialogResult> proprietà per determinare la modalità in cui è stata chiusa la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="05ea4-108">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3.  <span data-ttu-id="05ea4-109">Utilizzare il <xref:System.Windows.Forms.FontDialog.Font%2A> proprietà per impostare il tipo di carattere desiderato.</span><span class="sxs-lookup"><span data-stu-id="05ea4-109">Use the <xref:System.Windows.Forms.FontDialog.Font%2A> property to set the desired font.</span></span>  
  
     <span data-ttu-id="05ea4-110">Nell'esempio seguente, il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> gestore eventi viene aperto un <xref:System.Windows.Forms.FontDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="05ea4-110">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="05ea4-111">Quando un tipo di carattere viene scelto e l'utente fa clic su **OK**, <xref:System.Windows.Forms.FontDialog.Font%2A> proprietà di un <xref:System.Windows.Forms.TextBox> controllo nel form è impostato per il tipo di carattere selezionato.</span><span class="sxs-lookup"><span data-stu-id="05ea4-111">When a font is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.FontDialog.Font%2A> property of a <xref:System.Windows.Forms.TextBox> control that is on the form is set to the chosen font.</span></span> <span data-ttu-id="05ea4-112">Nell'esempio si presuppone il modulo contiene un <xref:System.Windows.Forms.Button> (controllo), un <xref:System.Windows.Forms.TextBox> (controllo) e un <xref:System.Windows.Forms.FontDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="05ea4-112">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a  <xref:System.Windows.Forms.TextBox> control, and a <xref:System.Windows.Forms.FontDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     <span data-ttu-id="05ea4-113">(Visual c# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="05ea4-113">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="05ea4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05ea4-114">See Also</span></span>  
 <xref:System.Windows.Forms.FontDialog>  
 [<span data-ttu-id="05ea4-115">Componente FontDialog</span><span class="sxs-lookup"><span data-stu-id="05ea4-115">FontDialog Component</span></span>](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
