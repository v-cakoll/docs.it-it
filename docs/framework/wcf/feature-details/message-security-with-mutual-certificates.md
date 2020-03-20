---
title: Protezione dei messaggi con certificati reciproci
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99d7a528-7ae4-4d39-a0f9-3066ea237de0
ms.openlocfilehash: e2aaf1a5e6ae1074a81c08fc798f22ea5e9ce139
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184614"
---
# <a name="message-security-with-mutual-certificates"></a>Protezione dei messaggi con certificati reciproci
Nello scenario seguente viene illustrato un servizio Windows Communication Foundation (WCF) e un client protetto tramite la modalità di sicurezza dei messaggi. Il client e il servizio sono autenticati mediante certificati.  
  
 Questo scenario è interoperativo perché utilizza WS-Security con la specifica X.509 Certificate Token Profile.  
  
> [!NOTE]
> Nello scenario non viene eseguita la negoziazione del certificato del servizio. È necessario che il certificato del servizio venga fornito al client prima di qualsiasi comunicazione. Il certificato del server può essere distribuito con l'applicazione o fornito in una comunicazione fuori banda.  
  
 ![Sicurezza dei messaggi con certificati reciprociMessage security with mutual certificates](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")  
  
|Caratteristica|Descrizione|  
|--------------------|-----------------|  
|Modalità di sicurezza|Message|  
|Interoperabilità|Sì, con WS-Security e client e servizi compatibili con X.509 Certificate Token Profile.|  
|Authentication|Autenticazione reciproca del server e del client.|  
|Integrità|Sì|  
|Riservatezza|Sì|  
|Trasporto|HTTP|  
|Associazione|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a>Service  
 Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente. Eseguire una delle operazioni seguenti:  
  
- Creare un servizio autonomo usando il codice senza alcuna configurazione.  
  
- Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.  
  
### <a name="code"></a>Codice  
 Nel codice seguente viene illustrato come creare un endpoint del servizio che utilizza la protezione del messaggio. Il servizio richiede un certificato per identificarsi.  
  
 [!code-csharp[C_SecurityScenarios#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#13)]
 [!code-vb[C_SecurityScenarios#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#13)]  
  
### <a name="configuration"></a>Configurazione  
 Per creare lo stesso servizio, è possibile utilizzare la configurazione seguente anziché il codice.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="serviceCredentialBehavior">  
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
      <service behaviorConfiguration="serviceCredentialBehavior"
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"  
                  bindingConfiguration="InteropCertificateBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="InteropCertificateBinding">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"  
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
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
 Il codice seguente crea il client. La modalità di sicurezza è impostata su Message e il tipo di credenziale client è impostato su Certificate.  
  
 [!code-csharp[C_SecurityScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#20)]
 [!code-vb[C_SecurityScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#20)]  
  
### <a name="configuration"></a>Configurazione  
 Il codice seguente consente di configurare il client. È necessario specificare un certificato client utilizzando [ \<clientCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md). Inoltre, il certificato del servizio viene specificato utilizzando il [ \<>defaultCertificate ](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"
                 storeLocation="CurrentUser"  
                 storeName="My"  
                 x509FindType="FindBySubjectName" />  
            <serviceCertificate>  
              <defaultCertificate findValue="Contoso.com"
                                  storeLocation="CurrentUser"  
                                  storeName="TrustedPeople"  
                                  x509FindType="FindBySubjectName" />  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate"
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                behaviorConfiguration="ClientCredentialsBehavior"  
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <certificate encodedValue="Encoded_Value_Not_Shown" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
- [Procedura: creare e installare certificati temporanei in WCF per la sicurezza del trasporto durante lo sviluppoHow to: Create and Install Temporary Certificates in WCF for Transport Security During Development](https://docs.microsoft.com/previous-versions/msp-n-p/ff648498(v=pandp.10))
