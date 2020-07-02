---
ms.openlocfilehash: 9b734fe960165b6d4b97b861cb3e8f31979f25c5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621211"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a><span data-ttu-id="3ec39-101">Rimuovere Ssl3 da TransportDefaults in WCF</span><span class="sxs-lookup"><span data-stu-id="3ec39-101">Remove Ssl3 from the WCF TransportDefaults</span></span>

#### <a name="details"></a><span data-ttu-id="3ec39-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3ec39-102">Details</span></span>

<span data-ttu-id="3ec39-103">Quando si usa NetTcp con la sicurezza del trasporto e un tipo di certificato con credenziali, il protocollo SSL 3 non è più un protocollo predefinito usato per negoziare una connessione protetta.</span><span class="sxs-lookup"><span data-stu-id="3ec39-103">When using NetTcp with transport security and a credential type of certificate, the SSL 3 protocol is no longer a default protocol used for negotiating a secure connection.</span></span> <span data-ttu-id="3ec39-104">Nella maggior parte dei casi non vi sarà alcun impatto sulle applicazioni esistenti, poiché TLS 1.0 è sempre stato incluso nell'elenco di protocolli per NetTcp.</span><span class="sxs-lookup"><span data-stu-id="3ec39-104">In most cases there should be no impact to existing apps as TLS 1.0 has always been included in the protocol list for NetTcp.</span></span> <span data-ttu-id="3ec39-105">Tutti i client esistenti devono essere in grado di negoziare una connessione usando almeno TLS1.0.</span><span class="sxs-lookup"><span data-stu-id="3ec39-105">All existing clients should be able to negotiate a connection using at least TLS1.0.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3ec39-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="3ec39-106">Suggestion</span></span>

<span data-ttu-id="3ec39-107">Se è necessario il protocollo Ssl3, usare uno dei meccanismi di configurazione seguenti per aggiungere SsI3 all'elenco dei protocolli negoziati.</span><span class="sxs-lookup"><span data-stu-id="3ec39-107">If Ssl3 is required, use one of the following configuration mechanisms to add Ssl3 to the list of negotiated protocols.</span></span><ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li><span data-ttu-id="3ec39-108">Sezione [&lt;sslStreamSecurity&gt; di &lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</span><span class="sxs-lookup"><span data-stu-id="3ec39-108">[&lt;sslStreamSecurity&gt; section of &lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</span></span></li></ul>

| <span data-ttu-id="3ec39-109">Nome</span><span class="sxs-lookup"><span data-stu-id="3ec39-109">Name</span></span>    | <span data-ttu-id="3ec39-110">Valore</span><span class="sxs-lookup"><span data-stu-id="3ec39-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3ec39-111">Scope</span><span class="sxs-lookup"><span data-stu-id="3ec39-111">Scope</span></span>   |<span data-ttu-id="3ec39-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3ec39-112">Edge</span></span>|
|<span data-ttu-id="3ec39-113">Version</span><span class="sxs-lookup"><span data-stu-id="3ec39-113">Version</span></span>|<span data-ttu-id="3ec39-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="3ec39-114">4.6.2</span></span>|
|<span data-ttu-id="3ec39-115">Type</span><span class="sxs-lookup"><span data-stu-id="3ec39-115">Type</span></span>|<span data-ttu-id="3ec39-116">Runtime</span><span class="sxs-lookup"><span data-stu-id="3ec39-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3ec39-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="3ec39-117">Affected APIs</span></span>

-<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType></li></ul>|
