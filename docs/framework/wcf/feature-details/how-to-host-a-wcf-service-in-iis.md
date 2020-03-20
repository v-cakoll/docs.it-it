---
title: 'Procedura: ospitare un servizio WCF in IIS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: 580b380a6c6349c6a4efa26e3eefe38bd660fa1b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184930"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a>Procedura: ospitare un servizio WCF in IIS
In questo argomento vengono descritti i passaggi di base necessari per creare un servizio Windows Communication Foundation (WCF) ospitato in Internet Information Services (IIS). Questo argomento presuppone la conoscenza di IIS e la comprensione dello strumento di gestione IIS per creare e gestire applicazioni IIS. Per ulteriori informazioni su IIS, vedere [Internet Information Services](https://www.iis.net/). Un servizio WCF che viene eseguito nell'ambiente IIS sfrutta appieno le funzionalità di IIS, ad esempio il riciclo dei processi, l'arresto inattivo, il monitoraggio dell'integrità del processo e l'attivazione basata su messaggi. Questa opzione di hosting richiede che IIS sia configurato correttamente, ma non richiede la scrittura di codice di hosting come parte dell'applicazione. È possibile utilizzare l'hosting IIS solo con un trasporto HTTP.  
  
 Per ulteriori informazioni sull'interazione tra WCF e ASP.NET, vedere [Servizi WCF e ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md). Per ulteriori informazioni sulla configurazione della protezione, vedere [Protezione](../../../../docs/framework/wcf/feature-details/security.md).  
  
 Per la copia di origine di questo esempio, vedere [IIS Hosting Using Inline Code](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).  
  
### <a name="to-create-a-service-hosted-by-iis"></a>Per creare un servizio ospitato da IIS  
  
1. Confermare che IIS sia installato e in esecuzione nel computer. Per ulteriori informazioni sull'installazione e la configurazione di IIS, vedere Installazione e configurazione di [IIS 7.0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista)  
  
2. Creare una nuova cartella per i file dell'applicazione denominata "IISHostedCalcService", assicurarsi che ASP.NET abbia accesso al contenuto della cartella e utilizzare lo strumento di gestione IIS per creare una nuova applicazione IIS fisicamente che si trova fisicamente in questa directory dell'applicazione. Quando si crea un alias per la directory dell'applicazione utilizzare "IISHostedCalc".  
  
3. Creare un nuovo file "service.svc" nella directory dell'applicazione. Modificare questo file aggiungendo @ServiceHost l'elemento seguente.  
  
   ```
   <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>
   ```  
  
4. Creare una sottodirectory App_Code all'interno della directory dell'applicazione.  
  
5. Creare un file di codice denominato Service.cs nella sottodirectory App_Code.  
  
6. Aggiungere le istruzioni using riportate di seguito all'inizio del file Service.cs.  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7. Aggiungere la seguente dichiarazione dello spazio dei nomi dopo le istruzioni using.  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8. Definire il contratto di servizio all'interno della dichiarazione dello spazio dei nomi come mostrato nel codice seguente.  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. Implementare il contratto di servizio dopo la sua definizione come illustrato nel codice seguente.  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. Creare un file denominato "Web.config" e aggiungere il codice di configurazione seguente nel file. In fase di esecuzione, l'infrastruttura WCF utilizza le informazioni per costruire un endpoint con cui le applicazioni client possono comunicare.  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]
  
     In questo esempio vengono specificati in modo esplicito gli endpoint del file di configurazione. Se non vengono aggiunti endpoint al servizio, il runtime aggiunge gli endpoint predefiniti. Per ulteriori informazioni sugli endpoint predefiniti, associazioni e comportamenti, vedere [configurazione semplificata](../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)i servizi WCF .  
  
11. Per assicurarsi che il servizio sia ospitato correttamente, aprire un'istanza di Internet Explorer e passare all'URL del servizio: `http://localhost/IISHostedCalc/Service.svc`  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato un elenco completo del codice per il servizio calcolatrice ospitato da IIS.  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)]
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)]
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a>Vedere anche

- [Host in Internet Information Services](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)
- [Servizi di hosting](../../../../docs/framework/wcf/hosting-services.md)
- [Servizi WCF e ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
- [Sicurezza](../../../../docs/framework/wcf/feature-details/security.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
