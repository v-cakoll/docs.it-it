---
ms.openlocfilehash: fb9436ec9e525afb497033775e34b6b636ced22d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621352"
---
### <a name="wcf-services-that-use-nettcp-with-ssl-security-and-md5-certificate-authentication"></a>Servizi WCF che usano NETTCP con sicurezza SSL e autenticazione dei certificati MD5

#### <a name="details"></a>Dettagli

.NET Framework 4.6 aggiunge TLS 1.1 e TLS 1.2 all'elenco dei protocolli predefiniti SSL WCF. Quando .NET Framework 4.6 o versione successiva è installato sia nei computer client che nei server, per la negoziazione viene usato TLS 1.2, che non supporta l'autenticazione dei certificati MD5. Di conseguenza, se un cliente usa un certificato MD5, il client WCF non riuscirà a connettersi al servizio WCF.

#### <a name="suggestion"></a>Suggerimento

È possibile risolvere questo problema in modo che un client WCF possa connettersi a un server WCF effettuando una delle operazioni seguenti:

- Aggiornare il certificato in modo che non usi l'algoritmo MD5. Si tratta della soluzione consigliata.
- Se l'associazione non è configurata in modo dinamico nel codice sorgente, aggiornare il file di configurazione dell'applicazione in modo che usi TLS 1.1 o una versione precedente del protocollo. In questo modo è possibile continuare a usare un certificato con l'algoritmo hash MD5.

> [!WARNING]
> Questa soluzione non è consigliata, poiché un certificato con l'algoritmo hash MD5 viene considerato non protetto.

Il file di configurazione seguente permette di effettuare queste operazioni:

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <netTcpBinding>
        <binding>
          <security mode= "None/Transport/Message/TransportWithMessageCredential" >
            <transport clientCredentialType="None/Windows/Certificate"
                       protectionLevel="None/Sign/EncryptAndSign"
                       sslProtocols="Ssl3/Tls1/Tls11">
            </transport>
          </security>
        </binding>
      </netTcpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

- Se l'associazione è configurata in modo dinamico nel codice sorgente, aggiornare la proprietà <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> in modo che usi TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType> o una versione precedente del protocollo nel codice sorgente.

> [!WARNING]
> Questa soluzione non è consigliata, poiché un certificato con l'algoritmo hash MD5 viene considerato non protetto.

| Nome    | Valore   |
|:--------|:--------|
| Scope   | Minorenne   |
| Version | 4.6     |
| Type    | Runtime |
