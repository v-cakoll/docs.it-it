---
title: 'Procedura: disabilitare le schede'
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
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 20674a93459f42a793ddf5f7ee5dffb1fa122d0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="1a362-102">Procedura: disabilitare le schede</span><span class="sxs-lookup"><span data-stu-id="1a362-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="1a362-103">In alcuni casi, è possibile limitare l'accesso ai dati disponibili all'interno dell'applicazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1a362-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="1a362-104">Un esempio potrebbe essere quando si dispone di dati visualizzati nelle pagine di un controllo scheda. gli amministratori potrebbe avere informazioni su una scheda che si desidera impedire agli utenti di livello inferiore o di guest.</span><span class="sxs-lookup"><span data-stu-id="1a362-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="1a362-105">Per disabilitare le schede a livello di codice</span><span class="sxs-lookup"><span data-stu-id="1a362-105">To disable tab pages programmatically</span></span>  
  
1.  <span data-ttu-id="1a362-106">Scrivere codice per gestire il controllo struttura a schede <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="1a362-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="1a362-107">Questo è l'evento generato quando l'utente passa da una scheda a quella successiva.</span><span class="sxs-lookup"><span data-stu-id="1a362-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2.  <span data-ttu-id="1a362-108">Verificare le credenziali.</span><span class="sxs-lookup"><span data-stu-id="1a362-108">Check credentials.</span></span> <span data-ttu-id="1a362-109">A seconda delle informazioni presentate, si consiglia di controllare l'accesso utente con il nome dell'utente o un'altra forma di credenziali prima di consentire all'utente di visualizzare la scheda.</span><span class="sxs-lookup"><span data-stu-id="1a362-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3.  <span data-ttu-id="1a362-110">Se l'utente dispone delle credenziali appropriate, è possibile visualizzare la scheda che è stato fatto clic.</span><span class="sxs-lookup"><span data-stu-id="1a362-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="1a362-111">Se l'utente non dispone delle credenziali appropriate, visualizzare una finestra di messaggio o altre interfacce utente che indica non hanno accesso e tornare alla scheda iniziale.</span><span class="sxs-lookup"><span data-stu-id="1a362-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1a362-112">Quando si implementa questa funzionalità nelle applicazioni di produzione, è possibile eseguire la verifica delle credenziali durante il modulo <xref:System.Windows.Forms.Form.Load> evento.</span><span class="sxs-lookup"><span data-stu-id="1a362-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="1a362-113">In questo modo sarà possibile nascondere la scheda prima che venga mostrata alcuna interfaccia utente, che è più chiaro.</span><span class="sxs-lookup"><span data-stu-id="1a362-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="1a362-114">La metodologia utilizzata di sotto (verifica delle credenziali e la disabilitazione della scheda durante il <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento) è solo a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="1a362-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4.  <span data-ttu-id="1a362-115">Facoltativamente, se si dispone di più di due schede, visualizzare una pagina della scheda diversa dall'originale.</span><span class="sxs-lookup"><span data-stu-id="1a362-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="1a362-116">Nell'esempio seguente, un <xref:System.Windows.Forms.CheckBox> viene utilizzato controllo anziché la verifica delle credenziali, come i criteri per l'accesso alla scheda variano a seconda dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1a362-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="1a362-117">Quando il <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento viene generato se la verifica delle credenziali (ovvero, la casella di controllo è selezionata) e la scheda selezionata è `TabPage2` (la scheda contenente informazioni riservate, in questo esempio), quindi `TabPage2` viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="1a362-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="1a362-118">In caso contrario, `TabPage3` viene visualizzata e viene visualizzata una finestra di messaggio all'utente, che indica che non dispone dei privilegi di accesso appropriati.</span><span class="sxs-lookup"><span data-stu-id="1a362-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="1a362-119">Il codice seguente si presuppone un form con un <xref:System.Windows.Forms.CheckBox> controllo (`CredentialCheck`) e un <xref:System.Windows.Forms.TabControl> controllo con tre schede.</span><span class="sxs-lookup"><span data-stu-id="1a362-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
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
  
     <span data-ttu-id="1a362-120">(Visual c#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1a362-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1a362-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a362-121">See Also</span></span>  
 [<span data-ttu-id="1a362-122">Panoramica del controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="1a362-122">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="1a362-123">Procedura: Aggiungere un controllo a un oggetto TabPage</span><span class="sxs-lookup"><span data-stu-id="1a362-123">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="1a362-124">Procedura: Aggiungere e rimuovere schede con il controllo TabControl di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1a362-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="1a362-125">Procedura: Modificare l'aspetto del controllo TabControl di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1a362-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
