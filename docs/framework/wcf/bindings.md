---
title: Associazioni di Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: bindings [WCF]
ms.assetid: 845df323-be53-4848-92ef-ba67a406484d
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b458c0491ec91cd528b40fb19e93b7948f8c059a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="windows-communication-foundation-bindings"></a><span data-ttu-id="620cf-102">Associazioni di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="620cf-102">Windows Communication Foundation Bindings</span></span>
<span data-ttu-id="620cf-103">Le associazioni specificano il modo in cui un endpoint di servizio di [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] comunica con altri endpoint.</span><span class="sxs-lookup"><span data-stu-id="620cf-103">Bindings specify how a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service endpoint communicates with other endpoints.</span></span> <span data-ttu-id="620cf-104">In parole semplici, un'associazione deve specificare il trasporto (ad esempio HTTP o TCP) da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="620cf-104">At its most basic, a binding must specify the transport (for example, HTTP or TCP) to use.</span></span> <span data-ttu-id="620cf-105">Le associazioni consentono inoltre di impostare altre caratteristiche, ad esempio la protezione e il supporto delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="620cf-105">You can also set other characteristics, such as security and transaction support, through bindings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="620cf-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="620cf-106">In This Section</span></span>  
 [<span data-ttu-id="620cf-107">Panoramica delle associazioni WCF</span><span class="sxs-lookup"><span data-stu-id="620cf-107">WCF Bindings Overview</span></span>](../../../docs/framework/wcf/bindings-overview.md)  
 <span data-ttu-id="620cf-108">Cenni preliminari sul funzionamento delle associazioni di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], sulle associazioni fornite dal sistema e su come sia possibile definirle o modificarle.</span><span class="sxs-lookup"><span data-stu-id="620cf-108">Overview of what [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] bindings do, what bindings the system provides, and how you can define or modify them.</span></span>  
  
 [<span data-ttu-id="620cf-109">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="620cf-109">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)  
 <span data-ttu-id="620cf-110">Elenco di associazioni incluse in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="620cf-110">A list of bindings included with [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="620cf-111">Queste associazioni coprono la maggior parte dei requisiti di sicurezza e dei modelli di messaggio.</span><span class="sxs-lookup"><span data-stu-id="620cf-111">These bindings cover the majority of security and message pattern requirements.</span></span>  
  
 [<span data-ttu-id="620cf-112">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="620cf-112">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 <span data-ttu-id="620cf-113">Un'associazione di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] contiene importanti informazioni che i client devono utilizzare per connettersi agli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="620cf-113">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] binding contains important information that clients must use to connect to service endpoints.</span></span>  
  
 [<span data-ttu-id="620cf-114">Configurazione delle associazioni per i servizi</span><span class="sxs-lookup"><span data-stu-id="620cf-114">Configuring Bindings for Services</span></span>](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)  
 <span data-ttu-id="620cf-115">La configurazione consente ad amministratori e programmi di installazione di personalizzare le associazioni per gli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="620cf-115">Configuration enables administrators and installers to customize the bindings for service endpoints.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="620cf-116">Riferimento</span><span class="sxs-lookup"><span data-stu-id="620cf-116">Reference</span></span>  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="620cf-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="620cf-117">Related Sections</span></span>  
 [<span data-ttu-id="620cf-118">Endpoint: Indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="620cf-118">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
  
 [<span data-ttu-id="620cf-119">Associazioni</span><span class="sxs-lookup"><span data-stu-id="620cf-119">Bindings</span></span>](../../../docs/framework/wcf/feature-details/bindings.md)  
  
## <a name="see-also"></a><span data-ttu-id="620cf-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="620cf-120">See Also</span></span>  
 [<span data-ttu-id="620cf-121">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="620cf-121">Custom Bindings</span></span>](../../../docs/framework/wcf/extending/custom-bindings.md)
