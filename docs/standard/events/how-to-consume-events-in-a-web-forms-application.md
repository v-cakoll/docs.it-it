---
title: 'Procedura: Usare eventi in un''applicazione Web Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [.NET Framework], Web Forms
- Web Forms controls, and events
- event handlers [.NET Framework], Web Forms
- events [.NET Framework], consuming
- Web Forms, event handling
ms.assetid: 73bf8638-c4ec-4069-b0bb-a1dc79b92e32
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bdb0a6be309f27348ba13bf93fd5aedd3c66a792
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-consume-events-in-a-web-forms-application"></a><span data-ttu-id="517a9-102">Procedura: Usare eventi in un'applicazione Web Form</span><span class="sxs-lookup"><span data-stu-id="517a9-102">How to: Consume Events in a Web Forms Application</span></span>
<span data-ttu-id="517a9-103">Uno scenario comune in applicazioni Web Form ASP.NET consiste nel compilare una pagina Web con controlli e quindi eseguire un'azione specifica in base che controllano l'utente fa clic.</span><span class="sxs-lookup"><span data-stu-id="517a9-103">A common scenario in ASP.NET Web Forms applications is to populate a webpage with controls, and then perform a specific action based on which control the user clicks.</span></span> <span data-ttu-id="517a9-104">Ad esempio, un <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> controllo genera un evento quando l'utente fa clic nella pagina Web.</span><span class="sxs-lookup"><span data-stu-id="517a9-104">For example, a <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> control raises an event when the user clicks it in the webpage.</span></span> <span data-ttu-id="517a9-105">La gestione dell'evento, l'applicazione consente di eseguire la logica dell'applicazione appropriata per tale pulsante.</span><span class="sxs-lookup"><span data-stu-id="517a9-105">By handling the event, your application can perform the appropriate application logic for that button click.</span></span>  
  
### <a name="to-handle-a-button-click-event-on-a-webpage"></a><span data-ttu-id="517a9-106">Per gestire un evento Click del pulsante in una pagina Web</span><span class="sxs-lookup"><span data-stu-id="517a9-106">To handle a button click event on a webpage</span></span>  
  
1.  <span data-ttu-id="517a9-107">Creare una pagina Web Form ASP.NET (pagina Web) che ha un <xref:System.Web.UI.WebControls.Button> controllare con il `OnClick` valore impostato per il nome del metodo che verrà definita nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="517a9-107">Create a ASP.NET Web Forms page (webpage) that has a <xref:System.Web.UI.WebControls.Button> control with the `OnClick` value set to the name of method that you will define in the next step.</span></span>  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2.  <span data-ttu-id="517a9-108">Definire un gestore eventi che soddisfi il <xref:System.Web.UI.WebControls.Button.Click> firma del delegato di evento e che ha il nome definito per il `OnClick` valore.</span><span class="sxs-lookup"><span data-stu-id="517a9-108">Define an event handler that matches the <xref:System.Web.UI.WebControls.Button.Click> event delegate signature and that has the name you defined for the `OnClick` value.</span></span>  
  
    ```csharp  
    protected void Button1_Click(object sender, EventArgs e)  
    {  
        // perform action  
    }  
    ```  
  
    ```vb  
    Protected Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' perform action  
    End Sub  
    ```  
  
     <span data-ttu-id="517a9-109">Il <xref:System.Web.UI.WebControls.Button.Click> evento utilizza il <xref:System.EventHandler> classe per il tipo delegato e <xref:System.EventArgs> classe per i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="517a9-109">The <xref:System.Web.UI.WebControls.Button.Click> event uses the <xref:System.EventHandler> class for the delegate type and the <xref:System.EventArgs> class for the event data.</span></span> <span data-ttu-id="517a9-110">Il framework della pagina ASP.NET genera automaticamente il codice che crea un'istanza di <xref:System.EventHandler> e aggiunge questa istanza di delegato per il <xref:System.Web.UI.WebControls.Button.Click> evento del <xref:System.Web.UI.WebControls.Button> istanza.</span><span class="sxs-lookup"><span data-stu-id="517a9-110">The ASP.NET page framework automatically generates code that creates an instance of <xref:System.EventHandler> and adds this delegate instance to the <xref:System.Web.UI.WebControls.Button.Click> event of the <xref:System.Web.UI.WebControls.Button> instance.</span></span>  
  
3.  <span data-ttu-id="517a9-111">Nel metodo del gestore è definito nel passaggio 2, aggiungere codice per eseguire azioni che sono necessari quando si verifica l'evento.</span><span class="sxs-lookup"><span data-stu-id="517a9-111">In the event handler method that you defined in step 2, add code to perform any actions that are required when the event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="517a9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="517a9-112">See Also</span></span>  
 [<span data-ttu-id="517a9-113">Eventi</span><span class="sxs-lookup"><span data-stu-id="517a9-113">Events</span></span>](../../../docs/standard/events/index.md)
