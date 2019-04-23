---
title: "Procedura: Usare eventi in un'applicazione Web Forms"
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc1dee9377200e4c9fd575b8dcd00982db45f249
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59317818"
---
# <a name="how-to-consume-events-in-a-web-forms-application"></a>Procedura: Usare eventi in un'applicazione Web Forms
Uno scenario comune in applicazioni Web Form ASP.NET consiste nel popolare una pagina Web con controlli e quindi eseguire un'azione specifica in base al controllo su cui fa clic l'utente. Ad esempio, un controllo <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> genera un evento quando l'utente fa clic nella pagina Web. Gestendo l'evento, l'applicazione può eseguire la logica appropriata per la pressione del pulsante.  
  
### <a name="to-handle-a-button-click-event-on-a-webpage"></a>Per gestire un evento Click del pulsante in una pagina Web  
  
1. Creare una pagina Web Form ASP.NET (pagina Web) che include un controllo <xref:System.Web.UI.WebControls.Button> con il valore `OnClick` impostato sul nome del metodo che verrà definito nel prossimo passaggio.  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2. Definire un gestore eventi che corrisponde alla firma del delegato dell'evento <xref:System.Web.UI.WebControls.Button.Click> e che include il nome definito per il valore `OnClick`.  
  
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
  
     L'evento <xref:System.Web.UI.WebControls.Button.Click> usa la classe <xref:System.EventHandler> per il tipo delegato e la classe <xref:System.EventArgs> per i dati dell'evento. Il framework della pagina ASP.NET genera automaticamente il codice che crea un'istanza di <xref:System.EventHandler> e aggiunge questa istanza di delegato all'evento <xref:System.Web.UI.WebControls.Button.Click> dell'istanza <xref:System.Web.UI.WebControls.Button>.  
  
3. Nel metodo del gestore eventi definito nel passaggio 2 aggiungere il codice per eseguire tutte le azioni necessarie quando si verifica l'evento.  
  
## <a name="see-also"></a>Vedere anche

- [Eventi](../../../docs/standard/events/index.md)
