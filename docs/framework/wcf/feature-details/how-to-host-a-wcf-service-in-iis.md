---
title: 'Procedura: ospitare un servizio WCF in IIS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: 326a270c4af38738c910828acd483070ab02ecd1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593087"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a>Procedura: ospitare un servizio WCF in IIS
In questo argomento vengono illustrati i passaggi di base necessari per creare un servizio Windows Communication Foundation (WCF) ospitato in Internet Information Services (IIS). Questo argomento presuppone la conoscenza di IIS e la comprensione dello strumento di gestione IIS per creare e gestire applicazioni IIS. Per ulteriori informazioni su IIS, vedere [Internet Information Services](https://www.iis.net/). Un servizio WCF in esecuzione nell'ambiente IIS sfrutta appieno le funzionalità di IIS, ad esempio il riciclo dei processi, l'arresto inattivo, il monitoraggio dell'integrità dei processi e l'attivazione basata su messaggi. Questa opzione di hosting richiede che IIS sia configurato correttamente, ma non richiede la scrittura di codice di hosting come parte dell'applicazione. È possibile utilizzare l'hosting IIS solo con un trasporto HTTP.  
  
 Per ulteriori informazioni sull'interazione tra WCF e ASP.NET, vedere [servizi WCF e ASP.NET](wcf-services-and-aspnet.md). Per ulteriori informazioni sulla configurazione della sicurezza, vedere [sicurezza](security.md).  
  
 Per la copia di origine di questo esempio, vedere la pagina relativa all' [hosting di IIS con il codice inline](../samples/iis-hosting-using-inline-code.md).  
  
### <a name="to-create-a-service-hosted-by-iis"></a>Per creare un servizio ospitato da IIS  
  
1. Confermare che IIS sia installato e in esecuzione nel computer. Per ulteriori informazioni sull'installazione e la configurazione di IIS, vedere [installazione e configurazione di iis 7,0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista)  
  
2. Creare una nuova cartella per i file dell'applicazione denominata "IISHostedCalcService", assicurarsi che ASP.NET abbia accesso al contenuto della cartella e utilizzare lo strumento di gestione IIS per creare una nuova applicazione IIS che si trova fisicamente in questa directory dell'applicazione. Quando si crea un alias per la directory dell'applicazione utilizzare "IISHostedCalc".  
  
3. Creare un nuovo file "service.svc" nella directory dell'applicazione. Modificare questo file aggiungendo l'elemento seguente @ServiceHost .  
  
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
  
     In questo esempio vengono specificati in modo esplicito gli endpoint del file di configurazione. Se non vengono aggiunti endpoint al servizio, il runtime aggiunge gli endpoint predefiniti. Per ulteriori informazioni sugli endpoint, le associazioni e i comportamenti predefiniti, vedere [Configurazione semplificata](../simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../samples/simplified-configuration-for-wcf-services.md).  
  
11. Per assicurarsi che il servizio sia ospitato correttamente, aprire un'istanza di Internet Explorer e passare all'URL del servizio: `http://localhost/IISHostedCalc/Service.svc`  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato un elenco completo del codice per il servizio calcolatrice ospitato da IIS.  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)]
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)]
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a>Vedere anche

- [Host in Internet Information Services](hosting-in-internet-information-services.md)
- [Servizi di hosting](../hosting-services.md)
- [Servizi WCF e ASP.NET](wcf-services-and-aspnet.md)
- [Sicurezza](security.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
