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
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="0e10e-102">Procedura: disabilitare le schede</span><span class="sxs-lookup"><span data-stu-id="0e10e-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="0e10e-103">In alcuni casi, è consigliabile limitare l'accesso ai dati disponibili all'interno dell'applicazione Windows Form.In some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span><span class="sxs-lookup"><span data-stu-id="0e10e-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="0e10e-104">Un esempio di questo potrebbe essere quando si dispone di dati visualizzati nelle schede di un controllo struttura a schede; gli amministratori potrebbero disporre di informazioni in una scheda che si desidera limitare agli utenti guest o di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="0e10e-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="0e10e-105">Per disabilitare le schede a livello di codiceTo disable tab pages programmatically</span><span class="sxs-lookup"><span data-stu-id="0e10e-105">To disable tab pages programmatically</span></span>  
  
1. <span data-ttu-id="0e10e-106">Scrivere il codice per gestire <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> l'evento del controllo struttura a schede.</span><span class="sxs-lookup"><span data-stu-id="0e10e-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="0e10e-107">Questo è l'evento che viene generato quando l'utente passa da una scheda alla successiva.</span><span class="sxs-lookup"><span data-stu-id="0e10e-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2. <span data-ttu-id="0e10e-108">Controllare le credenziali.</span><span class="sxs-lookup"><span data-stu-id="0e10e-108">Check credentials.</span></span> <span data-ttu-id="0e10e-109">A seconda delle informazioni presentate, è possibile controllare il nome utente con cui l'utente ha effettuato l'accesso o un'altra forma di credenziali prima di consentire all'utente di visualizzare la scheda.</span><span class="sxs-lookup"><span data-stu-id="0e10e-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3. <span data-ttu-id="0e10e-110">Se l'utente dispone delle credenziali appropriate, visualizzare la scheda su cui è stato fatto clic.</span><span class="sxs-lookup"><span data-stu-id="0e10e-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="0e10e-111">Se l'utente non dispone delle credenziali appropriate, visualizzare una finestra di messaggio o un'altra interfaccia utente che indica che non ha accesso e tornare alla scheda iniziale.</span><span class="sxs-lookup"><span data-stu-id="0e10e-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0e10e-112">Quando si implementa questa funzionalità nelle applicazioni di produzione, è <xref:System.Windows.Forms.Form.Load> possibile eseguire questo controllo delle credenziali durante l'evento del form.</span><span class="sxs-lookup"><span data-stu-id="0e10e-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="0e10e-113">Questo vi permetterà di nascondere la scheda prima di qualsiasi interfaccia utente viene mostrato, che è un approccio molto più pulito alla programmazione.</span><span class="sxs-lookup"><span data-stu-id="0e10e-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="0e10e-114">La metodologia utilizzata di seguito (verifica delle <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> credenziali e disabilitazione della scheda durante l'evento) è a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="0e10e-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4. <span data-ttu-id="0e10e-115">Facoltativamente, se si dispone di più di due schede, visualizzare una scheda diversa dall'originale.</span><span class="sxs-lookup"><span data-stu-id="0e10e-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="0e10e-116">Nell'esempio seguente, <xref:System.Windows.Forms.CheckBox> un controllo viene utilizzato al posto del controllo delle credenziali, poiché i criteri per l'accesso alla scheda variano a seconda dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0e10e-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="0e10e-117">Quando <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> viene generato l'evento, se il controllo delle credenziali è true (ovvero, la casella di controllo è selezionata) e la scheda selezionata è `TabPage2` (la scheda con le informazioni riservate, in questo esempio), `TabPage2` viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="0e10e-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="0e10e-118">In `TabPage3` caso contrario, viene visualizzata una finestra di messaggio e viene visualizzata una finestra di messaggio per l'utente, che indica che non disponeva dei privilegi di accesso appropriati.</span><span class="sxs-lookup"><span data-stu-id="0e10e-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="0e10e-119">Nel codice riportato di <xref:System.Windows.Forms.CheckBox> seguito`CredentialCheck`si presuppone <xref:System.Windows.Forms.TabControl> che un form con un controllo ( ) e un controllo con tre schede.</span><span class="sxs-lookup"><span data-stu-id="0e10e-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
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
  
     <span data-ttu-id="0e10e-120">(Visual C, Visual C Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="0e10e-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0e10e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e10e-121">See also</span></span>

- [<span data-ttu-id="0e10e-122">Cenni preliminari sul controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="0e10e-122">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="0e10e-123">Procedura: aggiungere un controllo a un oggetto TabPage</span><span class="sxs-lookup"><span data-stu-id="0e10e-123">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="0e10e-124">Procedura: aggiungere e rimuovere schede tramite il controllo TabControl Windows Form</span><span class="sxs-lookup"><span data-stu-id="0e10e-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="0e10e-125">Procedura: modificare l'aspetto del controllo TabControl Windows Form</span><span class="sxs-lookup"><span data-stu-id="0e10e-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
