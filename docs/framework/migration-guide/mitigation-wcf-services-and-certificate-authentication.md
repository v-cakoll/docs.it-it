---
title: 'Mitigazione: Autenticazione del certificato e servizi WCF'
ms.date: 03/30/2017
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc2e80a050e3b2e14663ba4bb67f650a16a6c619
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738313"
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a><span data-ttu-id="e4ffa-102">Mitigazione: Autenticazione del certificato e servizi WCF</span><span class="sxs-lookup"><span data-stu-id="e4ffa-102">Mitigation: WCF Services and Certificate Authentication</span></span>
<span data-ttu-id="e4ffa-103">.NET Framework 4.6 aggiunge TLS 1.1 e TLS 1.2 all'elenco predefinito dei controlli SSL WCF.</span><span class="sxs-lookup"><span data-stu-id="e4ffa-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL protocol default list.</span></span> <span data-ttu-id="e4ffa-104">Quando .NET Framework 4.6 o versione successiva è installato sia nei computer client che nei server, per la negoziazione viene usato TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="e4ffa-104">When both client and server machines have  the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="e4ffa-105">Impatto</span><span class="sxs-lookup"><span data-stu-id="e4ffa-105">Impact</span></span>  
 <span data-ttu-id="e4ffa-106">TLS 1.2 non supporta l'autenticazione dei certificati MD5.</span><span class="sxs-lookup"><span data-stu-id="e4ffa-106">TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="e4ffa-107">Di conseguenza, se un cliente usa un certificato SSL che a sua volta usa MD5 per l'algoritmo hash, il client di WCF non riesce a connettersi al servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="e4ffa-107">As a result, if a customer uses an SSL  certificate which uses MD5 for the hash algorithm, the WCF client fails to connect to the WCF service.</span></span> <span data-ttu-id="e4ffa-108">Per altre informazioni, vedere [Mitigazione: Autenticazione del certificato e servizi WCF](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e4ffa-108">For more information, see [Mitigation: WCF Services and Certificate Authentication](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="e4ffa-109">Mitigazione</span><span class="sxs-lookup"><span data-stu-id="e4ffa-109">Mitigation</span></span>  
 <span data-ttu-id="e4ffa-110">È possibile risolvere questo problema in modo che un client WCF possa connettersi a un server WCF effettuando una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4ffa-110">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>  
  
-   <span data-ttu-id="e4ffa-111">Aggiornare il certificato in modo che non usi l'algoritmo MD5.</span><span class="sxs-lookup"><span data-stu-id="e4ffa-111">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="e4ffa-112">Si tratta della soluzione consigliata.</span><span class="sxs-lookup"><span data-stu-id="e4ffa-112">This is the recommended solution.</span></span>  
  
-   <span data-ttu-id="e4ffa-113">Se l'associazione non è configurata in modo dinamico nel codice sorgente, aggiornare il file di configurazione dell'applicazione in modo che usi TLS 1.1 o una versione precedente del protocollo.</span><span class="sxs-lookup"><span data-stu-id="e4ffa-113">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="e4ffa-114">In questo modo è possibile continuare a usare un certificato con l'algoritmo hash MD5.</span><span class="sxs-lookup"><span data-stu-id="e4ffa-114">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="e4ffa-115">Questa soluzione non è consigliata, poiché un certificato con l'algoritmo hash MD5 viene considerato non protetto.</span><span class="sxs-lookup"><span data-stu-id="e4ffa-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>  
  
     <span data-ttu-id="e4ffa-116">Il file di configurazione seguente permette di effettuare queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="e4ffa-116">The following configuration file does this:</span></span>  
  
    ```xml  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding>  
                        <security mode= "None|Transport|Message|TransportWithMessageCredential" >  
                            <transport clientCredentialType="None|Windows|Certificate"  
                                                protectionLevel="None|Sign|EncryptAndSign"  
                                                sslProtocols="Ssl3|Tls1|Tls11">  
                            </transport>  
                        </security>  
                    </binding>  
                </netTcpBinding>  
            </bindings>  
        </system.ServiceModel>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="e4ffa-117">Se l'associazione è configurata in modo dinamico nel codice sorgente, aggiornare la proprietà <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> in modo che usi TLS 1.1(<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) o una versione precedente del protocollo nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="e4ffa-117">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) or an  earlier version of the protocol in the source code.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="e4ffa-118">Questa soluzione non è consigliata, poiché un certificato con l'algoritmo hash MD5 viene considerato non protetto.</span><span class="sxs-lookup"><span data-stu-id="e4ffa-118">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4ffa-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4ffa-119">See also</span></span>
- [<span data-ttu-id="e4ffa-120">Modifiche al runtime</span><span class="sxs-lookup"><span data-stu-id="e4ffa-120">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
