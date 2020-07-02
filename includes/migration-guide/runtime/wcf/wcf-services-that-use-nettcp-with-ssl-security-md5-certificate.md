---
ms.openlocfilehash: fb9436ec9e525afb497033775e34b6b636ced22d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621352"
---
### <a name="wcf-services-that-use-nettcp-with-ssl-security-and-md5-certificate-authentication"></a><span data-ttu-id="45dda-101">Servizi WCF che usano NETTCP con sicurezza SSL e autenticazione dei certificati MD5</span><span class="sxs-lookup"><span data-stu-id="45dda-101">WCF services that use NETTCP with SSL security and MD5 certificate authentication</span></span>

#### <a name="details"></a><span data-ttu-id="45dda-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="45dda-102">Details</span></span>

<span data-ttu-id="45dda-103">.NET Framework 4.6 aggiunge TLS 1.1 e TLS 1.2 all'elenco dei protocolli predefiniti SSL WCF.</span><span class="sxs-lookup"><span data-stu-id="45dda-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL default protocol list.</span></span> <span data-ttu-id="45dda-104">Quando .NET Framework 4.6 o versione successiva è installato sia nei computer client che nei server, per la negoziazione viene usato TLS 1.2, che non supporta l'autenticazione dei certificati MD5.</span><span class="sxs-lookup"><span data-stu-id="45dda-104">When both client and server machines have the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="45dda-105">Di conseguenza, se un cliente usa un certificato MD5, il client WCF non riuscirà a connettersi al servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="45dda-105">As a result, if a customer uses an MD5 certificate, the WCF client will fail to connect to the WCF service.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="45dda-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="45dda-106">Suggestion</span></span>

<span data-ttu-id="45dda-107">È possibile risolvere questo problema in modo che un client WCF possa connettersi a un server WCF effettuando una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="45dda-107">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>

- <span data-ttu-id="45dda-108">Aggiornare il certificato in modo che non usi l'algoritmo MD5.</span><span class="sxs-lookup"><span data-stu-id="45dda-108">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="45dda-109">Si tratta della soluzione consigliata.</span><span class="sxs-lookup"><span data-stu-id="45dda-109">This is the recommended solution.</span></span>
- <span data-ttu-id="45dda-110">Se l'associazione non è configurata in modo dinamico nel codice sorgente, aggiornare il file di configurazione dell'applicazione in modo che usi TLS 1.1 o una versione precedente del protocollo.</span><span class="sxs-lookup"><span data-stu-id="45dda-110">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="45dda-111">In questo modo è possibile continuare a usare un certificato con l'algoritmo hash MD5.</span><span class="sxs-lookup"><span data-stu-id="45dda-111">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>

> [!WARNING]
> <span data-ttu-id="45dda-112">Questa soluzione non è consigliata, poiché un certificato con l'algoritmo hash MD5 viene considerato non protetto.</span><span class="sxs-lookup"><span data-stu-id="45dda-112">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

<span data-ttu-id="45dda-113">Il file di configurazione seguente permette di effettuare queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="45dda-113">The following configuration file does this:</span></span>

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

- <span data-ttu-id="45dda-114">Se l'associazione è configurata in modo dinamico nel codice sorgente, aggiornare la proprietà <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> in modo che usi TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType> o una versione precedente del protocollo nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="45dda-114">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType> or an earlier version of the protocol in the source code.</span></span>

> [!WARNING]
> <span data-ttu-id="45dda-115">Questa soluzione non è consigliata, poiché un certificato con l'algoritmo hash MD5 viene considerato non protetto.</span><span class="sxs-lookup"><span data-stu-id="45dda-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

| <span data-ttu-id="45dda-116">Nome</span><span class="sxs-lookup"><span data-stu-id="45dda-116">Name</span></span>    | <span data-ttu-id="45dda-117">Valore</span><span class="sxs-lookup"><span data-stu-id="45dda-117">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="45dda-118">Scope</span><span class="sxs-lookup"><span data-stu-id="45dda-118">Scope</span></span>   | <span data-ttu-id="45dda-119">Minorenne</span><span class="sxs-lookup"><span data-stu-id="45dda-119">Minor</span></span>   |
| <span data-ttu-id="45dda-120">Version</span><span class="sxs-lookup"><span data-stu-id="45dda-120">Version</span></span> | <span data-ttu-id="45dda-121">4.6</span><span class="sxs-lookup"><span data-stu-id="45dda-121">4.6</span></span>     |
| <span data-ttu-id="45dda-122">Type</span><span class="sxs-lookup"><span data-stu-id="45dda-122">Type</span></span>    | <span data-ttu-id="45dda-123">Runtime</span><span class="sxs-lookup"><span data-stu-id="45dda-123">Runtime</span></span> |
