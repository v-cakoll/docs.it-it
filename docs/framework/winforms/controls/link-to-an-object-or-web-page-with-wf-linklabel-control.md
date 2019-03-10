---
title: 'Procedura: Collegarsi a un oggetto o Web Page con il controllo LinkLabel di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Windows Forms, linking to objects
- Web page link control
- linking [Windows Forms], to other forms
- Windows Forms, linking to Web pages
- links [Windows Forms], to other forms
- LinkLabel control [Windows Forms], linking to object or Web page
- LinkLabel control [Windows Forms], examples
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
ms.openlocfilehash: 34d6807b874596bd46f11ff90052ab85cc93b5d5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705189"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a>Procedura: Collegarsi a un oggetto o Web Page con il controllo LinkLabel di Windows Form
I moduli di Windows <xref:System.Windows.Forms.LinkLabel> controllo consente di creare collegamenti ipertestuali nel form. Quando si fa clic sul collegamento, è possibile modificare il colore per indicare che il collegamento è stato visitato. Per altre informazioni su come modificare il colore, vedere [come: Modificare l'aspetto del controllo Windows Form LinkLabel](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).  
  
## <a name="linking-to-another-form"></a>Collegamento a un altro formato  
  
#### <a name="to-link-to-another-form-with-a-linklabel-control"></a>Il collegamento a un altro form con un controllo LinkLabel  
  
1.  Impostare il <xref:System.Windows.Forms.LinkLabel.Text%2A> proprietà su un titolo appropriato.  
  
2.  Impostare il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà per determinare quale parte della didascalia verrà indicato come collegamento. Come è indicato dipende dalle proprietà correlate all'aspetto dell'etichetta del collegamento. Il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> valore è rappresentato da un <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> contenente due numeri, la posizione del carattere iniziale e il numero di caratteri. Il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà può essere impostata nella finestra proprietà o nel codice in modo analogo al seguente:  
  
    ```vb  
    ' In this code example, the link area has been set to begin  
    ' at the first character and extend for eight characters.  
    ' You may need to modify this based on the text entered in Step 1.  
    LinkLabel1.LinkArea = New LinkArea(0, 8)  
    ```  
  
    ```csharp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1.LinkArea = new LinkArea(0,8);  
    ```  
  
    ```cpp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1->LinkArea = LinkArea(0,8);  
    ```  
  
3.  Nel <xref:System.Windows.Forms.LinkLabel.LinkClicked> gestore dell'evento, richiamare il <xref:System.Windows.Forms.Form.Show%2A> metodo per aprire un'altra forma nel progetto e impostare il <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> proprietà `true`.  
  
    > [!NOTE]
    >  Un'istanza del <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> classe contiene un riferimento al <xref:System.Windows.Forms.LinkLabel> controllo che è stato selezionato, in modo che non è necessario eseguire il cast di `sender` oggetto.  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked(ByVal Sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       ' Show another form.  
       Dim f2 As New Form()  
       f2.Show  
       LinkLabel1.LinkVisited = True  
    End Sub  
    ```  
  
    ```csharp  
    protected void linkLabel1_LinkClicked(object sender, System. Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       // Show another form.  
       Form f2 = new Form();  
       f2.Show();  
       linkLabel1.LinkVisited = true;  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Show another form.  
          Form ^ f2 = new Form();  
          f2->Show();  
          linkLabel1->LinkVisited = true;  
       }  
    ```  
  
## <a name="linking-to-a-web-page"></a>Collegamento a una pagina Web  
 Il <xref:System.Windows.Forms.LinkLabel> controllo può essere usato anche per visualizzare una pagina Web con il browser predefinito.  
  
#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a>Per avviare Internet Explorer e collegamento a una pagina Web con un controllo LinkLabel  
  
1.  Impostare il <xref:System.Windows.Forms.LinkLabel.Text%2A> proprietà su un titolo appropriato.  
  
2.  Impostare il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà per determinare quale parte della didascalia verrà indicato come collegamento.  
  
3.  Nel <xref:System.Windows.Forms.LinkLabel.LinkClicked> gestore dell'evento, in corrispondenza di un blocco di gestione delle eccezioni, chiamare una seconda stored procedure che consente di impostare il <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> proprietà `true` e Usa il <xref:System.Diagnostics.Process.Start%2A> metodo per avviare il browser predefinito con un URL. Usare la <xref:System.Diagnostics.Process.Start%2A> è necessario aggiungere un riferimento al metodo il <xref:System.Diagnostics?displayProperty=nameWithType> dello spazio dei nomi.  
  
    > [!IMPORTANT]
    >  Se il codice seguente viene eseguito in un ambiente parzialmente attendibile (ad esempio in un'unità condivisa), il compilatore JIT non riesce quando il `VisitLink` viene chiamato il metodo. Il `System.Diagnostics.Process.Start` istruzione provoca una richiesta di collegamento che ha esito negativo. Per intercettare l'eccezione generata quando il `VisitLink` viene chiamato il metodo, il codice seguente garantisce che se il compilatore JIT non riesce, l'errore viene gestito normalmente.  
  
    ```vb  
    Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       Try  
          VisitLink()  
       Catch ex As Exception  
          ' The error message  
          MessageBox.Show("Unable to open link that was clicked.")  
       End Try  
    End Sub  
  
    Sub VisitLink()  
       ' Change the color of the link text by setting LinkVisited   
       ' to True.  
       LinkLabel1.LinkVisited = True  
       ' Call the Process.Start method to open the default browser   
       ' with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com")  
    End Sub  
    ```  
  
    ```csharp  
    private void linkLabel1_LinkClicked(object sender, System.Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       try  
       {  
          VisitLink();  
       }  
       catch (Exception ex )  
       {  
          MessageBox.Show("Unable to open link that was clicked.");  
       }  
    }  
  
    private void VisitLink()  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to true.  
       linkLabel1.LinkVisited = true;  
       //Call the Process.Start method to open the default browser   
       //with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com");  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          try  
          {  
             VisitLink();  
          }  
          catch (Exception ^ ex)  
          {  
             MessageBox::Show("Unable to open link that was clicked.");  
          }  
       }  
    private:  
       void VisitLink()  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to true.  
          linkLabel1->LinkVisited = true;  
          // Call the Process.Start method to open the default browser   
          // with a URL:  
          System::Diagnostics::Process::Start("http://www.microsoft.com");  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [Panoramica sul controllo LinkLabel](linklabel-control-overview-windows-forms.md)
- [Procedura: Modificare l'aspetto del controllo Windows Form LinkLabel](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [Controllo LinkLabel](linklabel-control-windows-forms.md)
