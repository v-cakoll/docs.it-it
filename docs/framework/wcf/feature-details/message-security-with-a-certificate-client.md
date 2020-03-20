---
title: Protezione dei messaggi con un client di certificato
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99770573-c815-4428-a38c-e4335c8bd7ce
ms.openlocfilehash: 3660877194931c2be5b9b1c9aa54e2595701697f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184652"
---
# <a name="message-security-with-a-certificate-client"></a>Protezione dei messaggi con un client di certificato
Nello scenario seguente viene illustrato un client Windows Communication Foundation (WCF) e un servizio protetto tramite la modalità di sicurezza dei messaggi. Sia il client che il servizio sono autenticati mediante certificati. Per ulteriori informazioni, vedere [Distributed Application Security](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).

 ![Screenshot che mostra un client con certificato.](./media/message-security-with-a-certificate-client/client-with-certificate.gif)  
  
 Per un'applicazione di esempio, vedere [Certificato di sicurezza dei](../../../../docs/framework/wcf/samples/message-security-certificate.md)messaggi .  

|Caratteristica|Descrizione|  
|--------------------|-----------------|  
|Modalità di sicurezza|Message|  
|Interoperabilità|Solo WCF|  
|Autenticazione (server)|Utilizzo del certificato del servizio|  
|Autenticazione (client)|Utilizzo del certificato client|  
|Integrità|Sì|  
|Riservatezza|Sì|  
|Trasporto|HTTP|  
|Associazione|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a>Service  
 Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente. Eseguire una delle operazioni seguenti:  
  
- Creare un servizio autonomo usando il codice senza alcuna configurazione.  
  
- Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.  
  
### <a name="code"></a>Codice  
 Nel codice seguente viene illustrato come creare un endpoint del servizio che utilizza la protezione dei messaggi per stabilire un contesto protetto.  
  
 [!code-csharp[C_SecurityScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#10)]
 [!code-vb[C_SecurityScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#10)]  
  
### <a name="configuration"></a>Configurazione  
 Invece del codice, è possibile usare la configurazione seguente:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"  
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
                  bindingConfiguration="MessageAndCertificateClient"
                  name="SecuredByClientCertificate"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a>Client  
 Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente. Eseguire una delle operazioni seguenti:  
  
- Creare un client autonomo usando il codice (e il codice client).  
  
- Creare un client che non definisce alcun indirizzo di endpoint. Usare invece il costruttore client che accetta il nome della configurazione come argomento. Ad esempio:  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a>Codice  
 Il codice seguente crea il client. L'associazione riguarda la protezione della modalità messaggio e il tipo di credenziale client è impostato su `Certificate`.  
  
 [!code-csharp[C_SecurityScenarios#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#17)]
 [!code-vb[C_SecurityScenarios#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#17)]  
  
### <a name="configuration"></a>Configurazione  
 Nella configurazione seguente il certificato client è specificato utilizzando un comportamento dell'endpoint. Per altre informazioni sui certificati, vedere [Utilizzo dei certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md). Il codice utilizza `identity` anche un elemento> <per specificare un DNS (Domain Name System) dell'identità del server prevista. Per ulteriori informazioni sull'identità, vedere [Identità e autenticazione del servizio](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"
               storeLocation="LocalMachine"  
              x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                behaviorConfiguration="endpointCredentialsBehavior"  
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Identità del servizio e autenticazione](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
