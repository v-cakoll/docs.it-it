---
title: Protezione dei messaggi tramite client con tipo di credenziale UserName
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
ms.openlocfilehash: 547c23509096b66c1fdbd46117a10f4de1692387
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212038"
---
# <a name="message-security-with-a-user-name-client"></a>Protezione dei messaggi tramite client con tipo di credenziale UserName
Nella figura seguente vengono illustrati un servizio Windows Communication Foundation (WCF) e un client protetti tramite la sicurezza a livello di messaggio. Il servizio viene autenticato con un certificato X.509. Il client esegue l'autenticazione utilizzando un nome utente e una password.  
  
 Per un'applicazione di esempio, vedere [nome utente](../../../../docs/framework/wcf/samples/message-security-user-name.md)per la sicurezza dei messaggi.  
  
 ![Sicurezza del messaggio con l'autenticazione del nome utente](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")  
  
|Caratteristica|Descrizione|  
|--------------------|-----------------|  
|Modalità di sicurezza|Messaggio|  
|Interoperabilità|Solo Windows Communication Foundation (WCF)|  
|Autenticazione (server)|La negoziazione iniziale richiede l'autenticazione server|  
|Autenticazione (client)|Nome utente/password|  
|Integrità|Sì, usando un contesto di sicurezza condiviso|  
|Riservatezza|Sì, usando un contesto di sicurezza condiviso|  
|Transport|HTTP|  
|Associazione|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a>Servizio  
 Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente. Effettuare una delle seguenti operazioni:  
  
- Creare un servizio autonomo usando il codice senza alcuna configurazione.  
  
- Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.  
  
### <a name="code"></a>Codice  
 Nel codice seguente viene illustrato come creare un endpoint del servizio che usa la protezione del messaggio.  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a>Configurazione di  
 Invece del codice, è possibile utilizzare la configurazione seguente:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My"     
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"  
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndUserName"  
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MessageAndUserName">  
          <security mode="Message">              
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a>Client  
  
### <a name="code"></a>Codice  
 Il codice seguente crea il client. L'associazione riguarda la protezione della modalità messaggio e il tipo di credenziale client è impostato su `UserName`. Il nome utente e la password possono essere specificati solo tramite codice (non è configurabile). Il codice per restituire il nome utente e la password non è riportato qui perché deve essere eseguito a livello di applicazione. Utilizzare, ad esempio, una finestra di dialogo Windows Form per chiedere i dati all'utente.  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a>Configurazione di  
 Nel codice seguente viene configurato il client. L'associazione riguarda la protezione della modalità messaggio e il tipo di credenziale client è impostato su `UserName`. Il nome utente e la password possono essere specificati solo tramite codice (non è configurabile).  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value ="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Sicurezza dei messaggi tramite nome utente](../../../../docs/framework/wcf/samples/message-security-user-name.md)
- [Identità del servizio e autenticazione](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
- [Modello di sicurezza per Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
