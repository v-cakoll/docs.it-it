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
ms.openlocfilehash: ace713a635b5d9c4b73f85cd3d378c0f1ff3dba1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107575"
---
# <a name="how-to-disable-tab-pages"></a>Procedura: Disabilitare le schede
In alcuni casi, è opportuno limitare l'accesso ai dati che sono disponibili all'interno dell'applicazione Windows Form. Un esempio potrebbe essere quando sono presenti dati visualizzati nelle pagine delle schede di un controllo scheda. gli amministratori può contenere informazioni su una pagina della scheda che si desidera impedire agli utenti di basso livello o guest.  
  
### <a name="to-disable-tab-pages-programmatically"></a>Per disabilitare le schede a livello di codice  
  
1.  Scrivere codice per gestire il controllo struttura a schede <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento. Questo è l'evento generato quando l'utente passa da una scheda a quella successiva.  
  
2.  Controllare le credenziali. A seconda delle informazioni presentate, è possibile controllare l'utente ha effettuato l'accesso con il nome dell'utente o un'altra forma di credenziali prima di consentire all'utente di visualizzare la scheda.  
  
3.  Se l'utente ha le credenziali appropriate, visualizzare la scheda in cui è stato fatto clic. Se l'utente non ha le credenziali appropriate, visualizzare una finestra di messaggio o altre interfacce utente che indica che essi non hanno accesso e tornare alla scheda iniziale.  
  
    > [!NOTE]
    >  Quando si implementa questa funzionalità nelle applicazioni di produzione, è possibile eseguire la verifica delle credenziali durante il modulo <xref:System.Windows.Forms.Form.Load> evento. In questo modo sarà possibile nascondere la scheda prima che qualsiasi interfaccia utente, il codice risulterà più chiaro. La metodologia utilizzata di sotto (controllo delle credenziali e la disabilitazione della scheda durante il <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> eventi) è a scopo illustrativo.  
  
4.  Facoltativamente, se si dispone di più di due schede, visualizzare una pagina della scheda diversa dall'originale.  
  
     Nell'esempio seguente, un <xref:System.Windows.Forms.CheckBox> controllo viene usato al posto di verifica le credenziali, come i criteri per l'accesso alla scheda variano a seconda dell'applicazione. Quando la <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento viene generato se la verifica delle credenziali (vale a dire, viene selezionata la casella di controllo) e la scheda selezionata viene `TabPage2` (la scheda con le informazioni riservate, in questo esempio), quindi `TabPage2` viene visualizzato. In caso contrario, `TabPage3` viene visualizzata e viene visualizzata una finestra di messaggio informa l'utente, non disponevano di privilegi di accesso appropriati. Il codice seguente si presuppone un form con un <xref:System.Windows.Forms.CheckBox> controllo (`CredentialCheck`) e un <xref:System.Windows.Forms.TabControl> controllo con tre schede.  
  
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
  
     (Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
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
- [Procedura: Aggiungere un controllo a una scheda](how-to-add-a-control-to-a-tab-page.md)
- [Procedura: Aggiungere e rimuovere schede con TabControl di Windows Forms](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [Procedura: Modificare l'aspetto di TabControl di Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
