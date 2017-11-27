---
title: 'Procedura: modificare l''aspetto del controllo LinkLabel di Windows Form'
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
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42aaef183178e7170d3046b4c5daefc8647f7cc1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a>Procedura: modificare l'aspetto del controllo LinkLabel di Windows Form
È possibile modificare il testo visualizzato per il <xref:System.Windows.Forms.LinkLabel> controllo in base alle diverse esigenze. Ad esempio, è pratica comune per indicare all'utente che è possibile fare clic sul testo impostando il testo da visualizzare in un colore specifico con un carattere di sottolineatura. L'utente fa clic sul testo, cambia il colore in un colore diverso. Per controllare questo comportamento, è possibile impostare cinque proprietà diverse: la <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, e <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> proprietà.  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a>Per modificare l'aspetto di un controllo LinkLabel  
  
1.  Impostare il <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> e <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> proprietà per i colori desiderati.  
  
     Questo può avvenire a livello di programmazione o in fase di progettazione nel **proprietà** finestra.  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2.  Impostare il <xref:System.Windows.Forms.LinkLabel.Text%2A> proprietà per una didascalia appropriata.  
  
     Questo può avvenire a livello di programmazione o in fase di progettazione nel **proprietà** finestra.  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3.  Impostare il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà per determinare quale parte della didascalia verrà indicata come collegamento.  
  
     Il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> valore è rappresentato con una <xref:System.Windows.Forms.LinkArea> contenente due numeri, la posizione del carattere iniziale e il numero di caratteri. Questo può avvenire a livello di programmazione o in fase di progettazione nel **proprietà** finestra.  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4.  Impostare il <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> proprietà <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, o <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.  
  
     Se è impostato su <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, la parte di didascalia determinata da <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> verrà sottolineata solo quando il puntatore è posizionato su di esso.  
  
5.  Nel <xref:System.Windows.Forms.LinkLabel.LinkClicked> gestore dell'evento, impostare il <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> proprietà `true`.  
  
     Quando è stato visitato un collegamento, è pratica comune per modificare l'aspetto in qualche modo, in genere in base al colore. Il testo verrà modificato il colore specificato da di <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> proprietà.  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>  
 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>  
 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>  
 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>  
 [Panoramica sul controllo LinkLabel](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)  
 [Procedura: Eseguire il collegamento a un oggetto o a una pagina Web con il controllo LinkLabel di Windows Form](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)  
 [Controllo LinkLabel](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
