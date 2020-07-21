---
title: 'Mitigazione: Autenticazione del certificato e servizi WCF'
description: Informazioni su come mitigare i problemi di autenticazione dei certificati dalle modifiche apportate all'elenco predefinito del protocollo SSL WCF in .NET Framework 4,6.
ms.date: 03/30/2017
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
ms.openlocfilehash: b6460e58bb32151003430d6573c4bcf1b514081b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475372"
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a><span data-ttu-id="3868b-103">Mitigazione: Autenticazione del certificato e servizi WCF</span><span class="sxs-lookup"><span data-stu-id="3868b-103">Mitigation: WCF Services and Certificate Authentication</span></span>

<span data-ttu-id="3868b-104">.NET Framework 4.6 aggiunge TLS 1.1 e TLS 1.2 all'elenco predefinito dei controlli SSL WCF.</span><span class="sxs-lookup"><span data-stu-id="3868b-104">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL protocol default list.</span></span> <span data-ttu-id="3868b-105">Quando .NET Framework 4.6 o versione successiva è installato sia nei computer client che nei server, per la negoziazione viene usato TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="3868b-105">When both client and server machines have  the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.</span></span>

## <a name="impact"></a><span data-ttu-id="3868b-106">Impatto</span><span class="sxs-lookup"><span data-stu-id="3868b-106">Impact</span></span>

<span data-ttu-id="3868b-107">TLS 1.2 non supporta l'autenticazione dei certificati MD5.</span><span class="sxs-lookup"><span data-stu-id="3868b-107">TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="3868b-108">Di conseguenza, se un cliente usa un certificato SSL che usa MD5 per l'algoritmo hash, il client WCF non riesce a connettersi al servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="3868b-108">As a result, if a customer uses an SSL certificate which uses MD5 for the hash algorithm, the WCF client fails to connect to the WCF service.</span></span> <span data-ttu-id="3868b-109">Per altre informazioni, vedere [Mitigation: WCF Services and Certificate Authentication](mitigation-wcf-services-and-certificate-authentication.md) (Mitigazione: Servizi WCF e autenticazione dei certificati).</span><span class="sxs-lookup"><span data-stu-id="3868b-109">For more information, see [Mitigation: WCF Services and Certificate Authentication](mitigation-wcf-services-and-certificate-authentication.md).</span></span>

## <a name="mitigation"></a><span data-ttu-id="3868b-110">Strategia di riduzione del rischio</span><span class="sxs-lookup"><span data-stu-id="3868b-110">Mitigation</span></span>

<span data-ttu-id="3868b-111">È possibile risolvere questo problema in modo che un client WCF possa connettersi a un server WCF effettuando una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3868b-111">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>

- <span data-ttu-id="3868b-112">Aggiornare il certificato in modo che non usi l'algoritmo MD5.</span><span class="sxs-lookup"><span data-stu-id="3868b-112">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="3868b-113">Si tratta della soluzione consigliata.</span><span class="sxs-lookup"><span data-stu-id="3868b-113">This is the recommended solution.</span></span>

- <span data-ttu-id="3868b-114">Se l'associazione non è configurata in modo dinamico nel codice sorgente, aggiornare il file di configurazione dell'applicazione in modo che usi TLS 1.1 o una versione precedente del protocollo.</span><span class="sxs-lookup"><span data-stu-id="3868b-114">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="3868b-115">In questo modo è possibile continuare a usare un certificato con l'algoritmo hash MD5.</span><span class="sxs-lookup"><span data-stu-id="3868b-115">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="3868b-116">Questa soluzione non è consigliata, poiché un certificato con l'algoritmo hash MD5 viene considerato non protetto.</span><span class="sxs-lookup"><span data-stu-id="3868b-116">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

  <span data-ttu-id="3868b-117">Il file di configurazione seguente permette di effettuare queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="3868b-117">The following configuration file does this:</span></span>

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
      </system.serviceModel>
  </configuration>
  ```

- <span data-ttu-id="3868b-118">Se l'associazione è configurata in modo dinamico nel codice sorgente, aggiornare la proprietà <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> in modo che usi TLS 1.1(<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) o una versione precedente del protocollo nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="3868b-118">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) or an  earlier version of the protocol in the source code.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="3868b-119">Questa soluzione non è consigliata, poiché un certificato con l'algoritmo hash MD5 viene considerato non protetto.</span><span class="sxs-lookup"><span data-stu-id="3868b-119">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

## <a name="see-also"></a><span data-ttu-id="3868b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3868b-120">See also</span></span>

- [<span data-ttu-id="3868b-121">Compatibilità tra le versioni</span><span class="sxs-lookup"><span data-stu-id="3868b-121">Application compatibility</span></span>](application-compatibility.md)
