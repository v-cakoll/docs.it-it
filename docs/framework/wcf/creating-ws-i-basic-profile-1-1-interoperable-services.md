---
title: Creazione di servizi interoperativi WS-I Basic Profile 1.1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6bef68c8ba433e902cfd50e59a3b343e3af08cd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a><span data-ttu-id="ee701-102">Creazione di servizi interoperativi WS-I Basic Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="ee701-102">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>
<span data-ttu-id="ee701-103">Per configurare l'interoperabilità di un endpoint del servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] con client del servizio Web [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ee701-103">To configure a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service endpoint to be interoperable with [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web service clients:</span></span>  
  
-   <span data-ttu-id="ee701-104">Utilizzare il tipo <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> come tipo di associazione per l'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="ee701-104">Use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
-   <span data-ttu-id="ee701-105">Non utilizzare funzionalità di callback e di contratto di sessioni né comportamenti della transazione nell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="ee701-105">Do not use callback and session contract features or transaction behaviors on your service endpoint</span></span>  
  
 <span data-ttu-id="ee701-106">È possibile, se lo si desidera, attivare nell'associazione il supporto per HTTPS e l'autenticazione del client a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="ee701-106">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span>  
  
 <span data-ttu-id="ee701-107">Le funzionalità seguenti della classe <xref:System.ServiceModel.BasicHttpBinding> richiedono altre funzionalità oltre a WS-I Basic Profile 1.1:</span><span class="sxs-lookup"><span data-stu-id="ee701-107">The following features of the <xref:System.ServiceModel.BasicHttpBinding> class require functionality beyond WS-I Basic Profile 1.1:</span></span>  
  
-   <span data-ttu-id="ee701-108">Codifica del messaggio MTOM (Message Transmission Optimization Mechanism, meccanismo di ottimizzazione della trasmissione dei messaggi) controllata dalla proprietà <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ee701-108">Message Transmission Optimization Mechanism (MTOM) message encoding controlled by the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="ee701-109">Lasciare l'impostazione predefinita di questa proprietà, ovvero <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> per non utilizzare MTOM.</span><span class="sxs-lookup"><span data-stu-id="ee701-109">Leave  this property at its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> to not use MTOM.</span></span>  
  
-   <span data-ttu-id="ee701-110">La sicurezza dei messaggi controllata dal valore di <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> fornisce supporto WS-Security conforme a WS-I Basic Security Profile 1.0.</span><span class="sxs-lookup"><span data-stu-id="ee701-110">Message security controlled by the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> value provides WS-Security support compliant with WS-I Basic Security Profile 1.0.</span></span> <span data-ttu-id="ee701-111">Lasciare l'impostazione predefinita di questa proprietà, ovvero <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> per non utilizzare WS-Security.</span><span class="sxs-lookup"><span data-stu-id="ee701-111">Leave this property at its default value, which is <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> to not use WS-Security.</span></span>  
  
 <span data-ttu-id="ee701-112">Per rendere i metadati un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servizio disponibile per [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], utilizzare gli strumenti di generazione client del servizio Web: [Web Services Description Language Tool (Wsdl.exe)](http://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88), [(strumento di individuazione Servizi Web Disco.exe)](http://msdn.microsoft.com/library/acd88078-c581-42bc-94ca-6633e2851979)e `Add Web Reference` funzionalità [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]; è necessario abilitare la pubblicazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="ee701-112">To make the metadata for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service available to [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], use the Web service client generation tools: [Web Services Description Language Tool (Wsdl.exe)](http://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88), [Web Services Discovery Tool (Disco.exe)](http://msdn.microsoft.com/library/acd88078-c581-42bc-94ca-6633e2851979), and the `Add Web Reference` feature in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]; you must enable metadata publication.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="ee701-113">[Gli endpoint dei metadati di pubblicazione](../../../docs/framework/wcf/publishing-metadata-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="ee701-113"> [Publishing Metadata Endpoints](../../../docs/framework/wcf/publishing-metadata-endpoints.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee701-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="ee701-114">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ee701-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee701-115">Description</span></span>  
 <span data-ttu-id="ee701-116">Esempio di codice seguente viene illustrato come aggiungere un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] endpoint compatibile con [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] client del servizio nel codice e, in alternativa, in un file di configurazione Web.</span><span class="sxs-lookup"><span data-stu-id="ee701-116">The following example code demonstrates how to add a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] endpoint that is compatible with [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web service clients in code and, alternatively, in a configuration file.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ee701-117">Codice</span><span class="sxs-lookup"><span data-stu-id="ee701-117">Code</span></span>  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ee701-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee701-118">See Also</span></span>  
 [<span data-ttu-id="ee701-119">Interoperabilità con servizi Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ee701-119">Interoperability with ASP.NET Web Services</span></span>](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
