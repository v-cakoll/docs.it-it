---
title: WCF e WebSocket
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e84bf7a94a6a6fa980e223daf0a6c7aaf489bb6e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-and-websockets"></a><span data-ttu-id="0902e-102">WCF e WebSocket</span><span class="sxs-lookup"><span data-stu-id="0902e-102">WCF and WebSockets</span></span>
<span data-ttu-id="0902e-103">Con .NET Framework 4.5 è stato introdotto il supporto per WebSocket in Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="0902e-103">The .NET Framework 4.5 introduces support for WebSockets in Windows Communication Foundation.</span></span>  <span data-ttu-id="0902e-104">Si tratta di una tecnologia efficiente e basata su standard che consente la comunicazione bidirezionale sulle porte 80 e 443 HTTP standard.</span><span class="sxs-lookup"><span data-stu-id="0902e-104">WebSockets is an efficient, standards-based technology that enables bidirectional communication over the standard HTTP ports 80 and 443.</span></span> <span data-ttu-id="0902e-105">L'utilizzo delle porte HTTP standard consente la comunicazione WebSocket attraverso il Web mediante intermediari.</span><span class="sxs-lookup"><span data-stu-id="0902e-105">The use of the standard HTTP ports allow WebSockets to communicate across the web through intermediaries.</span></span>  <span data-ttu-id="0902e-106">Sono state aggiunte due nuove associazioni standard per supportare la comunicazione tramite un trasporto WebSocket,</span><span class="sxs-lookup"><span data-stu-id="0902e-106">Two new standard bindings have been added to support communication over a WebSocket transport.</span></span> <span data-ttu-id="0902e-107"><xref:System.ServiceModel.NetHttpBinding> e <xref:System.ServiceModel.NetHttpsBinding>.</span><span class="sxs-lookup"><span data-stu-id="0902e-107"><xref:System.ServiceModel.NetHttpBinding> and <xref:System.ServiceModel.NetHttpsBinding>.</span></span> <span data-ttu-id="0902e-108">È possibile configurare impostazioni specifiche per WebSocket nel <xref:System.ServiceModel.Channels.HttpTransportBindingElement> accedendo il <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="0902e-108">WebSockets-specific settings can be configured on the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> by accessing the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> property.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0902e-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="0902e-109">In This Section</span></span>  
 [<span data-ttu-id="0902e-110">Uso di NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="0902e-110">Using the NetHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 <span data-ttu-id="0902e-111">Viene illustrato l'oggetto <xref:System.ServiceModel.NetHttpBinding> e la relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="0902e-111">Discusses the <xref:System.ServiceModel.NetHttpBinding> and how to configure it.</span></span>  
  
 [<span data-ttu-id="0902e-112">Procedura: Creare un servizio WCF che comunica tramite WebSockets</span><span class="sxs-lookup"><span data-stu-id="0902e-112">How to: Create a WCF Service that Communicates over WebSockets</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 <span data-ttu-id="0902e-113">Viene descritto come creare un servizio WCF che comunica tramite WebSockets.</span><span class="sxs-lookup"><span data-stu-id="0902e-113">Describes how to create a WCF service that communicates over Websockets.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0902e-114">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="0902e-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0902e-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="0902e-115">Related Sections</span></span>
