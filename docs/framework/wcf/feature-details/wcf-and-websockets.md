---
title: WCF e WebSocket
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: ac888db14ebd21c4aed2f717c1f71bed310b8388
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768732"
---
# <a name="wcf-and-websockets"></a><span data-ttu-id="45e55-102">WCF e WebSocket</span><span class="sxs-lookup"><span data-stu-id="45e55-102">WCF and WebSockets</span></span>
<span data-ttu-id="45e55-103">Con .NET Framework 4.5 è stato introdotto il supporto per WebSocket in Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="45e55-103">The .NET Framework 4.5 introduces support for WebSockets in Windows Communication Foundation.</span></span>  <span data-ttu-id="45e55-104">Si tratta di una tecnologia efficiente e basata su standard che consente la comunicazione bidirezionale sulle porte 80 e 443 HTTP standard.</span><span class="sxs-lookup"><span data-stu-id="45e55-104">WebSockets is an efficient, standards-based technology that enables bidirectional communication over the standard HTTP ports 80 and 443.</span></span> <span data-ttu-id="45e55-105">L'utilizzo delle porte HTTP standard consente la comunicazione WebSocket attraverso il Web mediante intermediari.</span><span class="sxs-lookup"><span data-stu-id="45e55-105">The use of the standard HTTP ports allow WebSockets to communicate across the web through intermediaries.</span></span>  <span data-ttu-id="45e55-106">Sono state aggiunte due nuove associazioni standard per supportare la comunicazione tramite un trasporto WebSocket,</span><span class="sxs-lookup"><span data-stu-id="45e55-106">Two new standard bindings have been added to support communication over a WebSocket transport.</span></span> <span data-ttu-id="45e55-107"><xref:System.ServiceModel.NetHttpBinding> e <xref:System.ServiceModel.NetHttpsBinding>.</span><span class="sxs-lookup"><span data-stu-id="45e55-107"><xref:System.ServiceModel.NetHttpBinding> and <xref:System.ServiceModel.NetHttpsBinding>.</span></span> <span data-ttu-id="45e55-108">Impostazioni specifiche per WebSocket possono essere configurate nel <xref:System.ServiceModel.Channels.HttpTransportBindingElement> accedendo il <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="45e55-108">WebSockets-specific settings can be configured on the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> by accessing the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> property.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="45e55-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="45e55-109">In This Section</span></span>  
 [<span data-ttu-id="45e55-110">Uso di NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="45e55-110">Using the NetHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 <span data-ttu-id="45e55-111">Viene illustrato l'oggetto <xref:System.ServiceModel.NetHttpBinding> e la relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="45e55-111">Discusses the <xref:System.ServiceModel.NetHttpBinding> and how to configure it.</span></span>  
  
 [<span data-ttu-id="45e55-112">Procedura: Creare un servizio WCF che comunica tramite WebSockets</span><span class="sxs-lookup"><span data-stu-id="45e55-112">How to: Create a WCF Service that Communicates over WebSockets</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 <span data-ttu-id="45e55-113">Viene descritto come creare un servizio WCF che comunica tramite WebSockets.</span><span class="sxs-lookup"><span data-stu-id="45e55-113">Describes how to create a WCF service that communicates over Websockets.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="45e55-114">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="45e55-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="45e55-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="45e55-115">Related Sections</span></span>
