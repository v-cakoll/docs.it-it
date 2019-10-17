---
title: Creazione di servizi interoperativi WS-I Basic Profile 1.1
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: eb1cd12c45a276d5c3cb14f89205fff618121abc
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320136"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a><span data-ttu-id="95a7e-102">Creazione di servizi interoperativi WS-I Basic Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="95a7e-102">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>
<span data-ttu-id="95a7e-103">Per configurare un endpoint del servizio WCF per l'interoperabilità con i client del servizio Web ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="95a7e-103">To configure a WCF service endpoint to be interoperable with ASP.NET Web service clients:</span></span>  
  
- <span data-ttu-id="95a7e-104">Utilizzare il tipo <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> come tipo di associazione per l'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="95a7e-104">Use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
- <span data-ttu-id="95a7e-105">Non utilizzare funzioni di callback e di contratto di sessioni né comportamenti della transazione nell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="95a7e-105">Do not use callback and session contract features or transaction behaviors on your service endpoint</span></span>  
  
 <span data-ttu-id="95a7e-106">È possibile, se lo si desidera, attivare nell'associazione il supporto per HTTPS e l'autenticazione del client a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="95a7e-106">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span>  
  
 <span data-ttu-id="95a7e-107">Le funzionalità seguenti della classe <xref:System.ServiceModel.BasicHttpBinding> richiedono altre funzionalità oltre a WS-I Basic Profile 1.1:</span><span class="sxs-lookup"><span data-stu-id="95a7e-107">The following features of the <xref:System.ServiceModel.BasicHttpBinding> class require functionality beyond WS-I Basic Profile 1.1:</span></span>  
  
- <span data-ttu-id="95a7e-108">Codifica del messaggio MTOM (Message Transmission Optimization Mechanism, meccanismo di ottimizzazione della trasmissione dei messaggi) controllata dalla proprietà <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="95a7e-108">Message Transmission Optimization Mechanism (MTOM) message encoding controlled by the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="95a7e-109">Lasciare l'impostazione predefinita di questa proprietà, ovvero <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> per non utilizzare MTOM.</span><span class="sxs-lookup"><span data-stu-id="95a7e-109">Leave  this property at its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> to not use MTOM.</span></span>  
  
- <span data-ttu-id="95a7e-110">La sicurezza dei messaggi controllata dal valore di <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> fornisce supporto WS-Security conforme a WS-I Basic Security Profile 1.0.</span><span class="sxs-lookup"><span data-stu-id="95a7e-110">Message security controlled by the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> value provides WS-Security support compliant with WS-I Basic Security Profile 1.0.</span></span> <span data-ttu-id="95a7e-111">Lasciare l'impostazione predefinita di questa proprietà, ovvero <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> per non utilizzare WS-Security.</span><span class="sxs-lookup"><span data-stu-id="95a7e-111">Leave this property at its default value, which is <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> to not use WS-Security.</span></span>  
  
 <span data-ttu-id="95a7e-112">Per rendere disponibili i metadati per un servizio WCF a ASP.NET, utilizzare gli strumenti di generazione client del servizio Web: [Web Services Description Language strumento (WSDL. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29), [strumento di individuazione servizi Web (disco. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29)e la funzionalità `Add Web Reference` in Visual Studio. è necessario abilitare la pubblicazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="95a7e-112">To make the metadata for a WCF service available to ASP.NET, use the Web service client generation tools: [Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29), [Web Services Discovery Tool (Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29), and the `Add Web Reference` feature in Visual Studio; you must enable metadata publication.</span></span> <span data-ttu-id="95a7e-113">Per ulteriori informazioni, vedere [pubblicazione di endpoint dei metadati](publishing-metadata-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="95a7e-113">For more information, see [Publishing Metadata Endpoints](publishing-metadata-endpoints.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="95a7e-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="95a7e-114">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="95a7e-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95a7e-115">Description</span></span>  
 <span data-ttu-id="95a7e-116">Nell'esempio di codice seguente viene illustrato come aggiungere un endpoint WCF compatibile con i client del servizio Web ASP.NET nel codice e, in alternativa, in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="95a7e-116">The following example code demonstrates how to add a WCF endpoint that is compatible with ASP.NET Web service clients in code and, alternatively, in a configuration file.</span></span>  
  
### <a name="code"></a><span data-ttu-id="95a7e-117">Codice</span><span class="sxs-lookup"><span data-stu-id="95a7e-117">Code</span></span>  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a><span data-ttu-id="95a7e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95a7e-118">See also</span></span>

- [<span data-ttu-id="95a7e-119">Interoperabilità con servizi Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="95a7e-119">Interoperability with ASP.NET Web Services</span></span>](./feature-details/interop-with-aspnet-web-services.md)
