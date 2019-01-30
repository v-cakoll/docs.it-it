---
title: Sicurezza del trasporto con un client anonimo - WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: 20d7e59ba2b4b9dedc0b0daff1c1aa9c5210e61b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260385"
---
# <a name="transport-security-with-an-anonymous-client"></a>Sicurezza del trasporto con un client anonimo

Questo scenario di Windows Communication Foundation (WCF) Usa sicurezza del trasporto (HTTPS) per garantire la riservatezza e integrità. È necessario che il server sia autenticato con un certificato SSL (Secure Sockets Layer) e che il client ritenga attendibile il certificato del server. Il client non viene autenticato da alcun meccanismo ed è pertanto anonimo.

Per un'applicazione di esempio, vedere [la sicurezza del trasporto WS](../samples/ws-transport-security.md). Per altre informazioni sulla sicurezza del trasporto, vedere [Cenni preliminari sulla sicurezza di trasporto](transport-security-overview.md).

Per altre informazioni sull'uso di un certificato con un servizio, vedere [Working with Certificates](working-with-certificates.md) e [come: Configurare una porta con un certificato SSL](how-to-configure-a-port-with-an-ssl-certificate.md).

![Uso della sicurezza del trasporto con un client anonimo](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|Caratteristica|Descrizione|
|--------------------|-----------------|
|Modalità di sicurezza|Trasporto|
|Interoperabilità|Con i servizi Web e i client esistenti|
|Autenticazione (server)<br /><br /> Autenticazione (client)|Yes<br /><br /> Livello di applicazione (Nessun supporto WCF)|
|Integrità|Sì|
|Riservatezza|Sì|
|Trasporto|HTTPS|
|Binding|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a>Servizio

Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente. Eseguire una delle operazioni seguenti:

- Creare un servizio autonomo usando il codice senza alcuna configurazione.

- Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.

### <a name="code"></a>Codice

Nel codice seguente viene illustrato come creare un endpoint utilizzando la protezione del trasporto:

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a>Configurazione

Nel codice seguente viene impostato lo stesso endpoint utilizzando la configurazione. Il client non viene autenticato da alcun meccanismo ed è pertanto anonimo.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="ServiceModel.Calculator">
        <endpoint address="https://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="WSHttpBinding_ICalculator"
                  name="SecuredByTransportEndpoint"
                  contract="ServiceModel.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator">
          <security mode="Transport">
            <transport clientCredentialType="None" />
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

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a>Codice

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a>Configurazione

Per configurare il servizio, è possibile utilizzare la configurazione seguente anziché il codice.

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="https://machineName/Calculator"
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"
                name="WSHttpBinding_ICalculator" />
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- [Panoramica della sicurezza](security-overview.md)
- [Sicurezza del trasporto WS](../samples/ws-transport-security.md)
- [Panoramica della sicurezza del trasporto](transport-security-overview.md)
- [Modello di sicurezza per Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))