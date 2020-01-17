---
title: Sicurezza dei messaggi con un client Windows senza negoziazione delle credenziali
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fc07a26c-cbee-41c5-8fb0-329085fef749
ms.openlocfilehash: d3b05a1786131a119d516edeba0d6e8e24289f87
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212034"
---
# <a name="message-security-with-a-windows-client-without-credential-negotiation"></a>Sicurezza dei messaggi con un client Windows senza negoziazione delle credenziali

Nello scenario seguente vengono illustrati un client e un servizio Windows Communication Foundation (WCF) protetti dal protocollo Kerberos.

Il servizio e il client sono nello stesso dominio o sono entrambi in domini attendibili.

> [!NOTE]
> La differenza tra questo scenario e la [sicurezza dei messaggi con un client Windows](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) è che questo scenario non negozia le credenziali del servizio con il servizio prima di inviare il messaggio dell'applicazione. Inoltre, poiché ciò richiede il protocollo Kerberos, questo scenario richiede un dominio Windows.

![Sicurezza del messaggio senza negoziazione delle credenziali](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")

|Caratteristica|Descrizione|
|--------------------|-----------------|
|Modalità di sicurezza|Messaggio|
|Interoperabilità|Sì, WS-Security con client compatibili con il profilo del token Kerberos|
|Autenticazione (server)|Autenticazione reciproca del server e del client|
|Autenticazione (client)|Autenticazione reciproca del server e del client|
|Integrità|Sì|
|Riservatezza|Sì|
|Transport|HTTP|
|Associazione|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a>Servizio

Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente. Effettuare una delle seguenti operazioni:

- Creare un servizio autonomo usando il codice senza alcuna configurazione.

- Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.

### <a name="code"></a>Codice

Il codice seguente crea un endpoint del servizio che usa la sicurezza del messaggio. Il codice disabilita la negoziazione della credenziale del servizio e la definizione di un token del contesto di sicurezza (SCT, Security Context Token).

> [!NOTE]
> Per usare il tipo di credenziale di Windows senza negoziazione, l'account utente del servizio deve avere accesso al nome dell'entità servizio (SPN, Service Principal Name) registrato con il dominio di Active Directory. Tale operazione può essere eseguita in due modi:

1. Usare l'account `NetworkService` o `LocalSystem` per eseguire il servizio. Poiché questi account hanno accesso al nome SPN del computer stabilito quando il computer viene aggiunto al dominio Active Directory, WCF genera automaticamente l'elemento SPN appropriato all'interno dell'endpoint del servizio nei metadati del servizio (descrizione dei servizi Web Lingua o WSDL.

2. Usare un account di dominio Active Directory arbitrario per eseguire il servizio. In questo caso è necessario definire un SPN per questo account di dominio. A tale scopo è possibile usare l'utilità Setspn.exe. Una volta creato il nome SPN per l'account del servizio, configurare WCF per la pubblicazione di tale SPN nei client del servizio tramite i relativi metadati (WSDL). Questa operazione viene eseguita impostando l'identità per l'endpoint esposto o tramite un file di configurazione dell'applicazione o tramite codice. Nell'esempio seguente l'identità viene pubblicata a livello di programmazione.

Per ulteriori informazioni sui nomi SPN, sul protocollo Kerberos e Active Directory, vedere [supplemento tecnico Kerberos per Windows](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10)). Per altre informazioni sulle identità degli endpoint, vedere [modalità di autenticazione di SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).

[!code-csharp[C_SecurityScenarios#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#12)]
[!code-vb[C_SecurityScenarios#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#12)]

### <a name="configuration"></a>Configurazione di

Invece del codice, è possibile usare la configurazione seguente:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors />
    <services>
      <service behaviorConfiguration="" name="ServiceModel.Calculator">
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="KerberosBinding"
                  name="WSHttpBinding_ICalculator"
                  contract="ServiceModel.ICalculator"
                  listenUri="net.tcp://localhost/metadata" >
         <identity>
            <servicePrincipalName value="service_spn_name" />
         </identity>
        </endpoint>
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="KerberosBinding">
          <security>
            <message negotiateServiceCredential="false"
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

Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente. Effettuare una delle seguenti operazioni:

- Creare un client autonomo usando il codice (e il codice client).

- Creare un client che non definisce alcun indirizzo di endpoint. Usare invece il costruttore client che accetta il nome della configurazione come argomento. Ad esempio:

  [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
  [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a>Codice

Nel codice seguente viene configurato il client. La modalità di sicurezza è impostata su Messaggio e il tipo di credenziale client è impostato su Windows. Le proprietà <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> e <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> sono impostate su `false`.

> [!NOTE]
> Per usare un tipo di credenziale di Windows senza negoziazione, il client deve essere configurato con il nome di entità servizio dell'account del servizio prima di iniziare la comunicazione con il servizio. Il client usa il nome dell'entità servizio (SPN) per ottenere il token Kerberos per autenticare e proteggere la comunicazione con il servizio. L'esempio seguente mostra come configurare il client con l'SPN del servizio. Se si utilizza lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il client, l'SPN del servizio verrà propagato automaticamente al client dai metadati (WSDL) del servizio, se i metadati del servizio contengono tali informazioni. Per ulteriori informazioni su come configurare il servizio in modo da includere il relativo nome SPN nei metadati del servizio, vedere la sezione "servizio" più avanti in questo argomento.
>
> Per ulteriori informazioni sui nomi SPN, Kerberos e Active Directory, vedere [supplemento tecnico Kerberos per Windows](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10)). Per ulteriori informazioni sulle identità degli endpoint, vedere [l'](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) argomento relativo alle modalità di autenticazione di SecurityBindingElement.

[!code-csharp[C_SecurityScenarios#19](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#19)]
[!code-vb[C_SecurityScenarios#19](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#19)]

### <a name="configuration"></a>Configurazione di

Nel codice seguente viene configurato il client. Si noti che è necessario impostare l'elemento [\<servicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) in modo che corrisponda al nome SPN del servizio come registrato per l'account del servizio nel dominio Active Directory.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Message">
            <message clientCredentialType="Windows"
                     negotiateServiceCredential="false"
                     establishSecurityContext="false" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="http://localhost/Calculator"
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"
                name="WSHttpBinding_ICalculator">
        <identity>
          <servicePrincipalName value="service_spn_name" />
        </identity>
      </endpoint>
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- [Panoramica della sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Identità del servizio e autenticazione](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [Modello di sicurezza per Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
