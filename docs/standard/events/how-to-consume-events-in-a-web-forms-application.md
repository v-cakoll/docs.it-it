---
title: "Procedura: Usare eventi in un'applicazione Web Form"
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 1f95fd0dcc12f2d4e47ee07e1e6bb15d91000f0f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73124789"
---
# <a name="how-to-consume-events-in-a-web-forms-application"></a><span data-ttu-id="63c55-102">Procedura: Usare eventi in un'applicazione Web Form</span><span class="sxs-lookup"><span data-stu-id="63c55-102">How to: Consume Events in a Web Forms Application</span></span>
<span data-ttu-id="63c55-103">Uno scenario comune in applicazioni Web Form ASP.NET consiste nel popolare una pagina Web con controlli e quindi eseguire un'azione specifica in base al controllo su cui fa clic l'utente.</span><span class="sxs-lookup"><span data-stu-id="63c55-103">A common scenario in ASP.NET Web Forms applications is to populate a webpage with controls, and then perform a specific action based on which control the user clicks.</span></span> <span data-ttu-id="63c55-104">Ad esempio, un controllo <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> genera un evento quando l'utente fa clic nella pagina Web.</span><span class="sxs-lookup"><span data-stu-id="63c55-104">For example, a <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> control raises an event when the user clicks it in the webpage.</span></span> <span data-ttu-id="63c55-105">Gestendo l'evento, l'applicazione può eseguire la logica appropriata per la pressione del pulsante.</span><span class="sxs-lookup"><span data-stu-id="63c55-105">By handling the event, your application can perform the appropriate application logic for that button click.</span></span>  
  
### <a name="to-handle-a-button-click-event-on-a-webpage"></a><span data-ttu-id="63c55-106">Per gestire un evento Click del pulsante in una pagina Web</span><span class="sxs-lookup"><span data-stu-id="63c55-106">To handle a button click event on a webpage</span></span>  
  
1. <span data-ttu-id="63c55-107">Creare una pagina Web Form ASP.NET (pagina Web) che include un controllo <xref:System.Web.UI.WebControls.Button> con il valore `OnClick` impostato sul nome del metodo che verrà definito nel prossimo passaggio.</span><span class="sxs-lookup"><span data-stu-id="63c55-107">Create a ASP.NET Web Forms page (webpage) that has a <xref:System.Web.UI.WebControls.Button> control with the `OnClick` value set to the name of method that you will define in the next step.</span></span>  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2. <span data-ttu-id="63c55-108">Definire un gestore eventi che corrisponde alla firma del delegato dell'evento <xref:System.Web.UI.WebControls.Button.Click> e che include il nome definito per il valore `OnClick`.</span><span class="sxs-lookup"><span data-stu-id="63c55-108">Define an event handler that matches the <xref:System.Web.UI.WebControls.Button.Click> event delegate signature and that has the name you defined for the `OnClick` value.</span></span>  
  
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
  
     <span data-ttu-id="63c55-109">L'evento <xref:System.Web.UI.WebControls.Button.Click> usa la classe <xref:System.EventHandler> per il tipo delegato e la classe <xref:System.EventArgs> per i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="63c55-109">The <xref:System.Web.UI.WebControls.Button.Click> event uses the <xref:System.EventHandler> class for the delegate type and the <xref:System.EventArgs> class for the event data.</span></span> <span data-ttu-id="63c55-110">Il framework della pagina ASP.NET genera automaticamente il codice che crea un'istanza di <xref:System.EventHandler> e aggiunge questa istanza di delegato all'evento <xref:System.Web.UI.WebControls.Button.Click> dell'istanza <xref:System.Web.UI.WebControls.Button>.</span><span class="sxs-lookup"><span data-stu-id="63c55-110">The ASP.NET page framework automatically generates code that creates an instance of <xref:System.EventHandler> and adds this delegate instance to the <xref:System.Web.UI.WebControls.Button.Click> event of the <xref:System.Web.UI.WebControls.Button> instance.</span></span>  
  
3. <span data-ttu-id="63c55-111">Nel metodo del gestore eventi definito nel passaggio 2 aggiungere il codice per eseguire tutte le azioni necessarie quando si verifica l'evento.</span><span class="sxs-lookup"><span data-stu-id="63c55-111">In the event handler method that you defined in step 2, add code to perform any actions that are required when the event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63c55-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63c55-112">See also</span></span>

- [<span data-ttu-id="63c55-113">Events</span><span class="sxs-lookup"><span data-stu-id="63c55-113">Events</span></span>](../../../docs/standard/events/index.md)
