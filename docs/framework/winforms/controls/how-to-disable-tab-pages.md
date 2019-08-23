---
title: 'Procedura: Disabilitare le schede'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: 888228c28dce591b237be16b6a321afee0105208
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967143"
---
# <a name="how-to-disable-tab-pages"></a>Procedura: Disabilitare le schede
In alcuni casi, è possibile limitare l'accesso ai dati disponibili all'interno del Windows Forms Application. Un esempio potrebbe essere quando i dati vengono visualizzati nelle schede di un controllo struttura a schede; gli amministratori possono disporre di informazioni su una scheda che si desidera limitare dagli utenti guest o di livello inferiore.  
  
### <a name="to-disable-tab-pages-programmatically"></a>Per disabilitare le schede a livello di codice  
  
1. Scrivere il codice per gestire l' <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento del controllo Tab. Si tratta dell'evento generato quando l'utente passa da una scheda a quella successiva.  
  
2. Verificare le credenziali. A seconda delle informazioni presentate, potrebbe essere necessario controllare il nome utente con cui l'utente ha eseguito l'accesso o altre forme di credenziali prima di consentire all'utente di visualizzare la scheda.  
  
3. Se l'utente dispone delle credenziali appropriate, visualizzare la scheda su cui è stato fatto clic. Se l'utente non dispone delle credenziali appropriate, Visualizza una finestra di messaggio o un'altra interfaccia utente che indica che non è possibile accedervi e tornare alla scheda iniziale.  
  
    > [!NOTE]
    > Quando si implementa questa funzionalità nelle applicazioni di produzione, è possibile eseguire questo controllo delle credenziali durante l' <xref:System.Windows.Forms.Form.Load> evento del modulo. In questo modo sarà possibile nascondere la scheda prima di visualizzare un'interfaccia utente, un approccio molto più semplice alla programmazione. La metodologia utilizzata di seguito (controllando le credenziali e disabilitando <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> la scheda durante l'evento) è a scopo illustrativo.  
  
4. Facoltativamente, se si dispone di più di due schede, visualizzare una scheda diversa dall'originale.  
  
     Nell'esempio seguente viene usato un <xref:System.Windows.Forms.CheckBox> controllo anziché controllare le credenziali, in quanto i criteri per l'accesso alla scheda variano in base all'applicazione. Quando viene <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> generato l'evento, se il controllo delle credenziali è true (ovvero la casella di controllo è selezionata) e la scheda selezionata è `TabPage2` (la scheda con le informazioni riservate, in `TabPage2` questo esempio), viene visualizzato. In caso `TabPage3` contrario, viene visualizzato e viene visualizzata una finestra di messaggio all'utente che indica che non dispone dei privilegi di accesso appropriati. Il codice riportato di seguito presuppone un form <xref:System.Windows.Forms.CheckBox> con un`CredentialCheck`controllo () <xref:System.Windows.Forms.TabControl> e un controllo con tre schede.  
  
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
  
     (Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica del controllo TabControl](tabcontrol-control-overview-windows-forms.md)
- [Procedura: Aggiungere un controllo a una pagina della scheda](how-to-add-a-control-to-a-tab-page.md)
- [Procedura: Aggiungere e rimuovere schede con il controllo TabControl Windows Forms](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [Procedura: Modificare l'aspetto del Windows Forms TabControl](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
