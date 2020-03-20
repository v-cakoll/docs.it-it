---
title: Modifica dell'aspetto del controllo LinkLabel
ms.date: 03/30/2017
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
ms.openlocfilehash: df66991289373a05fc7c27b7768a96643e3bbae0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142130"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a>Procedura: modificare l'aspetto del controllo LinkLabel di Windows Form
È possibile modificare il testo <xref:System.Windows.Forms.LinkLabel> visualizzato dal controllo in base a diversi scopi. Ad esempio, è pratica comune indicare all'utente che è possibile fare clic sul testo impostando il testo in modo che venga visualizzato in un colore specifico con una sottolineatura. Dopo che l'utente fa clic sul testo, il colore assume un colore diverso. Per controllare questo comportamento, è possibile <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>impostare cinque proprietà diverse: le proprietà , <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>e <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> .  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a>Per modificare l'aspetto di un controllo LinkLabel  
  
1. Impostare <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> le proprietà e per i colori desiderati.  
  
     Questa operazione può essere eseguita a livello di codice o in fase di progettazione nel **proprietà** finestra.  
  
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
  
2. Impostare <xref:System.Windows.Forms.LinkLabel.Text%2A> la proprietà su una didascalia appropriata.  
  
     Questa operazione può essere eseguita a livello di codice o in fase di progettazione nel **proprietà** finestra.  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. Impostare <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> la proprietà per determinare quale parte della didascalia verrà indicata come collegamento.  
  
     Il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> valore è <xref:System.Windows.Forms.LinkArea> rappresentato da un contenente due numeri, la posizione del carattere iniziale e il numero di caratteri. Questa operazione può essere eseguita a livello di codice o in fase di progettazione nel **proprietà** finestra.  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. Impostare <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> la <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline> <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>proprietà <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>su , , o .  
  
     Se è impostata su <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, la <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> parte della didascalia determinata da verrà sottolineata solo quando il puntatore viene posizionato su di essa.  
  
5. <xref:System.Windows.Forms.LinkLabel.LinkClicked> Nel gestore eventi impostare la proprietà su <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> `true`.  
  
     Quando un link è stato visitato, è pratica comune cambiare il suo aspetto in qualche modo, di solito per colore. Il testo cambierà nel colore <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> specificato dalla proprietà .  
  
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

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [Panoramica del controllo LinkLabel](linklabel-control-overview-windows-forms.md)
- [Procedura: eseguire il collegamento a un oggetto o a una pagina Web con il controllo LinkLabel di Windows Form](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Controllo LinkLabel](linklabel-control-windows-forms.md)
