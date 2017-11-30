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
# <a name="how-to-consume-events-in-a-web-forms-application"></a>Procedura: Usare eventi in un'applicazione Web Form
Uno scenario comune in applicazioni Web Form ASP.NET consiste nel compilare una pagina Web con controlli e quindi eseguire un'azione specifica in base che controllano l'utente fa clic. Ad esempio, un <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> controllo genera un evento quando l'utente fa clic nella pagina Web. La gestione dell'evento, l'applicazione consente di eseguire la logica dell'applicazione appropriata per tale pulsante.  
  
### <a name="to-handle-a-button-click-event-on-a-webpage"></a>Per gestire un evento Click del pulsante in una pagina Web  
  
1.  Creare una pagina Web Form ASP.NET (pagina Web) che ha un <xref:System.Web.UI.WebControls.Button> controllare con il `OnClick` valore impostato per il nome del metodo che verrà definita nel passaggio successivo.  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2.  Definire un gestore eventi che soddisfi il <xref:System.Web.UI.WebControls.Button.Click> firma del delegato di evento e che ha il nome definito per il `OnClick` valore.  
  
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
  
     Il <xref:System.Web.UI.WebControls.Button.Click> evento utilizza il <xref:System.EventHandler> classe per il tipo delegato e <xref:System.EventArgs> classe per i dati dell'evento. Il framework della pagina ASP.NET genera automaticamente il codice che crea un'istanza di <xref:System.EventHandler> e aggiunge questa istanza di delegato per il <xref:System.Web.UI.WebControls.Button.Click> evento del <xref:System.Web.UI.WebControls.Button> istanza.  
  
3.  Nel metodo del gestore è definito nel passaggio 2, aggiungere codice per eseguire azioni che sono necessari quando si verifica l'evento.  
  
## <a name="see-also"></a>Vedere anche  
 [Eventi](../../../docs/standard/events/index.md)
