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
ms.openlocfilehash: 9074aedb81a485267dc4faff92e0fe8d0d3b467f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182164"
---
# <a name="how-to-disable-tab-pages"></a>Procedura: disabilitare le schede
In alcuni casi, è consigliabile limitare l'accesso ai dati disponibili all'interno dell'applicazione Windows Form.In some occasions, you will want to restrict access to data that is available within your Windows Forms application. Un esempio di questo potrebbe essere quando si dispone di dati visualizzati nelle schede di un controllo struttura a schede; gli amministratori potrebbero disporre di informazioni in una scheda che si desidera limitare agli utenti guest o di livello inferiore.  
  
### <a name="to-disable-tab-pages-programmatically"></a>Per disabilitare le schede a livello di codiceTo disable tab pages programmatically  
  
1. Scrivere il codice per gestire <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> l'evento del controllo struttura a schede. Questo è l'evento che viene generato quando l'utente passa da una scheda alla successiva.  
  
2. Controllare le credenziali. A seconda delle informazioni presentate, è possibile controllare il nome utente con cui l'utente ha effettuato l'accesso o un'altra forma di credenziali prima di consentire all'utente di visualizzare la scheda.  
  
3. Se l'utente dispone delle credenziali appropriate, visualizzare la scheda su cui è stato fatto clic. Se l'utente non dispone delle credenziali appropriate, visualizzare una finestra di messaggio o un'altra interfaccia utente che indica che non ha accesso e tornare alla scheda iniziale.  
  
    > [!NOTE]
    > Quando si implementa questa funzionalità nelle applicazioni di produzione, è <xref:System.Windows.Forms.Form.Load> possibile eseguire questo controllo delle credenziali durante l'evento del form. Questo vi permetterà di nascondere la scheda prima di qualsiasi interfaccia utente viene mostrato, che è un approccio molto più pulito alla programmazione. La metodologia utilizzata di seguito (verifica delle <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> credenziali e disabilitazione della scheda durante l'evento) è a scopo illustrativo.  
  
4. Facoltativamente, se si dispone di più di due schede, visualizzare una scheda diversa dall'originale.  
  
     Nell'esempio seguente, <xref:System.Windows.Forms.CheckBox> un controllo viene utilizzato al posto del controllo delle credenziali, poiché i criteri per l'accesso alla scheda variano a seconda dell'applicazione. Quando <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> viene generato l'evento, se il controllo delle credenziali è true (ovvero, la casella di controllo è selezionata) e la scheda selezionata è `TabPage2` (la scheda con le informazioni riservate, in questo esempio), `TabPage2` viene visualizzata. In `TabPage3` caso contrario, viene visualizzata una finestra di messaggio e viene visualizzata una finestra di messaggio per l'utente, che indica che non disponeva dei privilegi di accesso appropriati. Nel codice riportato di <xref:System.Windows.Forms.CheckBox> seguito`CredentialCheck`si presuppone <xref:System.Windows.Forms.TabControl> che un form con un controllo ( ) e un controllo con tre schede.  
  
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
  
     (Visual C, Visual C Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sul controllo TabControl](tabcontrol-control-overview-windows-forms.md)
- [Procedura: aggiungere un controllo a un oggetto TabPage](how-to-add-a-control-to-a-tab-page.md)
- [Procedura: aggiungere e rimuovere schede tramite il controllo TabControl Windows Form](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [Procedura: modificare l'aspetto del controllo TabControl Windows Form](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
