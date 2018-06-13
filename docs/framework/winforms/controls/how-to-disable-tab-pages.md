---
title: 'Procedura: disabilitare le schede'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: 94d8522a71fcd565ae8f994d73ffe4c46fcf7ce3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534267"
---
# <a name="how-to-disable-tab-pages"></a>Procedura: disabilitare le schede
In alcuni casi, è possibile limitare l'accesso ai dati disponibili all'interno dell'applicazione Windows Form. Un esempio potrebbe essere quando si dispone di dati visualizzati nelle pagine di un controllo scheda. gli amministratori potrebbe avere informazioni su una scheda che si desidera impedire agli utenti di livello inferiore o di guest.  
  
### <a name="to-disable-tab-pages-programmatically"></a>Per disabilitare le schede a livello di codice  
  
1.  Scrivere codice per gestire il controllo struttura a schede <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento. Questo è l'evento generato quando l'utente passa da una scheda a quella successiva.  
  
2.  Verificare le credenziali. A seconda delle informazioni presentate, si consiglia di controllare l'accesso utente con il nome dell'utente o un'altra forma di credenziali prima di consentire all'utente di visualizzare la scheda.  
  
3.  Se l'utente dispone delle credenziali appropriate, è possibile visualizzare la scheda che è stato fatto clic. Se l'utente non dispone delle credenziali appropriate, visualizzare una finestra di messaggio o altre interfacce utente che indica non hanno accesso e tornare alla scheda iniziale.  
  
    > [!NOTE]
    >  Quando si implementa questa funzionalità nelle applicazioni di produzione, è possibile eseguire la verifica delle credenziali durante il modulo <xref:System.Windows.Forms.Form.Load> evento. In questo modo sarà possibile nascondere la scheda prima che venga mostrata alcuna interfaccia utente, che è più chiaro. La metodologia utilizzata di sotto (verifica delle credenziali e la disabilitazione della scheda durante il <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento) è solo a scopo illustrativo.  
  
4.  Facoltativamente, se si dispone di più di due schede, visualizzare una pagina della scheda diversa dall'originale.  
  
     Nell'esempio seguente, un <xref:System.Windows.Forms.CheckBox> viene utilizzato controllo anziché la verifica delle credenziali, come i criteri per l'accesso alla scheda variano a seconda dell'applicazione. Quando il <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento viene generato se la verifica delle credenziali (ovvero, la casella di controllo è selezionata) e la scheda selezionata è `TabPage2` (la scheda contenente informazioni riservate, in questo esempio), quindi `TabPage2` viene visualizzato. In caso contrario, `TabPage3` viene visualizzata e viene visualizzata una finestra di messaggio all'utente, che indica che non dispone dei privilegi di accesso appropriati. Il codice seguente si presuppone un form con un <xref:System.Windows.Forms.CheckBox> controllo (`CredentialCheck`) e un <xref:System.Windows.Forms.TabControl> controllo con tre schede.  
  
    ```vb  
    Private Sub TabControl1_SelectedIndexChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles TabControl1.SelectedIndexChanged  
       ' Check Credentials Here  
  
       If CredentialCheck.Checked = True And _   
       TabControl1.SelectedTab Is TabPage2 Then  
          TabControl1.SelectedTab = TabPage2  
       ElseIf CredentialCheck.Checked = False _   
       And TabControl1.SelectedTab Is TabPage2 Then  
          MessageBox.Show _   
         ("Unable to load tab. You have insufficient access privileges.")  
          TabControl1.SelectedTab = TabPage3  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void tabControl1_SelectedIndexChanged(object sender, System.EventArgs e)  
    {  
        // Check Credentials Here  
  
        if ((CredentialCheck.Checked == true) && (tabControl1.SelectedTab == tabPage2))   
        {  
            tabControl1.SelectedTab = tabPage2;  
        }  
        else if ((CredentialCheck.Checked == false) && (tabControl1.SelectedTab == tabPage2))  
        {  
            MessageBox.Show("Unable to load tab. You have insufficient access privileges.");  
            tabControl1.SelectedTab = tabPage3;  
        }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void tabControl1_SelectedIndexChanged(  
          System::Object ^ sender,  
          System::EventArgs ^  e)  
       {  
          // Check Credentials Here  
          if ((CredentialCheck->Checked == true) &&  
              (tabControl1->SelectedTab == tabPage2))  
          {  
             tabControl1->SelectedTab = tabPage2;  
          }  
          else if ((CredentialCheck->Checked == false) &&  
                   (tabControl1->SelectedTab == tabPage2))  
          {  
             MessageBox::Show(String::Concat("Unable to load tab. ",  
                "You have insufficient access privileges."));  
             tabControl1->SelectedTab = tabPage3;  
          }  
       }  
    ```  
  
     (Visual c#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica del controllo TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [Procedura: Aggiungere un controllo a un oggetto TabPage](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [Procedura: Aggiungere e rimuovere schede con il controllo TabControl di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 [Procedura: Modificare l'aspetto del controllo TabControl di Windows Form](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
