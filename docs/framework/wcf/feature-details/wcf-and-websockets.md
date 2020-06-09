---
title: WCF e WebSocket
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: df4a251eb5a570c9fedf19d385a027e23481afed
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594946"
---
# <a name="wcf-and-websockets"></a><span data-ttu-id="3f9d0-102">WCF e WebSocket</span><span class="sxs-lookup"><span data-stu-id="3f9d0-102">WCF and WebSockets</span></span>
<span data-ttu-id="3f9d0-103">Con .NET Framework 4.5 è stato introdotto il supporto per WebSocket in Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="3f9d0-103">The .NET Framework 4.5 introduces support for WebSockets in Windows Communication Foundation.</span></span>  <span data-ttu-id="3f9d0-104">Si tratta di una tecnologia efficiente e basata su standard che consente la comunicazione bidirezionale sulle porte 80 e 443 HTTP standard.</span><span class="sxs-lookup"><span data-stu-id="3f9d0-104">WebSockets is an efficient, standards-based technology that enables bidirectional communication over the standard HTTP ports 80 and 443.</span></span> <span data-ttu-id="3f9d0-105">L'utilizzo delle porte HTTP standard consente la comunicazione WebSocket attraverso il Web mediante intermediari.</span><span class="sxs-lookup"><span data-stu-id="3f9d0-105">The use of the standard HTTP ports allow WebSockets to communicate across the web through intermediaries.</span></span>  <span data-ttu-id="3f9d0-106">Sono state aggiunte due nuove associazioni standard per supportare la comunicazione tramite un trasporto WebSocket,</span><span class="sxs-lookup"><span data-stu-id="3f9d0-106">Two new standard bindings have been added to support communication over a WebSocket transport.</span></span> <span data-ttu-id="3f9d0-107"><xref:System.ServiceModel.NetHttpBinding> e <xref:System.ServiceModel.NetHttpsBinding>.</span><span class="sxs-lookup"><span data-stu-id="3f9d0-107"><xref:System.ServiceModel.NetHttpBinding> and <xref:System.ServiceModel.NetHttpsBinding>.</span></span> <span data-ttu-id="3f9d0-108">Le impostazioni specifiche di WebSockets possono essere configurate su <xref:System.ServiceModel.Channels.HttpTransportBindingElement> tramite l'accesso alla <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="3f9d0-108">WebSockets-specific settings can be configured on the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> by accessing the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> property.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="3f9d0-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3f9d0-109">In This Section</span></span>  
 [<span data-ttu-id="3f9d0-110">Uso di NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="3f9d0-110">Using the NetHttpBinding</span></span>](using-the-nethttpbinding.md)  
 <span data-ttu-id="3f9d0-111">Viene illustrato l'oggetto <xref:System.ServiceModel.NetHttpBinding> e la relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="3f9d0-111">Discusses the <xref:System.ServiceModel.NetHttpBinding> and how to configure it.</span></span>  
  
 [<span data-ttu-id="3f9d0-112">Procedura: creare un servizio WCF che comunica tramite WebSockets</span><span class="sxs-lookup"><span data-stu-id="3f9d0-112">How to: Create a WCF Service that Communicates over WebSockets</span></span>](how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 <span data-ttu-id="3f9d0-113">Viene descritto come creare un servizio WCF che comunica tramite WebSockets.</span><span class="sxs-lookup"><span data-stu-id="3f9d0-113">Describes how to create a WCF service that communicates over Websockets.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3f9d0-114">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="3f9d0-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3f9d0-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="3f9d0-115">Related Sections</span></span>
