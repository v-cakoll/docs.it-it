---
title: Associazioni WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 384e5bb05ba4263f245f6901b84e2388ea19bd73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488624"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="21074-102">Associazioni WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="21074-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="21074-103">In questo argomento vengono illustrate le modalità di costruzione delle associazioni predefinite per lo scambio di metadati per i vari trasporti.</span><span class="sxs-lookup"><span data-stu-id="21074-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="21074-104">Associazioni predefinite</span><span class="sxs-lookup"><span data-stu-id="21074-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="21074-105">Nome associazione predefinita</span><span class="sxs-lookup"><span data-stu-id="21074-105">Default Binding Name</span></span>|<span data-ttu-id="21074-106">Modalità di costruzione dell'associazione</span><span class="sxs-lookup"><span data-stu-id="21074-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="21074-107">MexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="21074-107">MexHttpBinding</span></span>|<span data-ttu-id="21074-108">Una classe <xref:System.ServiceModel.WSHttpBinding> con protezione a livello di trasporto attivata.</span><span class="sxs-lookup"><span data-stu-id="21074-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="21074-109">MexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="21074-109">MexHttpsBinding</span></span>|<span data-ttu-id="21074-110">Una classe <xref:System.ServiceModel.WSHttpBinding> che supporta la protezione a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="21074-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="21074-111">MexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="21074-111">MexNamedPipeBinding</span></span>|<span data-ttu-id="21074-112">Una classe <xref:System.ServiceModel.Channels.CustomBinding> con un elemento <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> che utilizza valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="21074-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="21074-113">MexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="21074-113">MexTcpBinding</span></span>|<span data-ttu-id="21074-114">Una classe <xref:System.ServiceModel.Channels.CustomBinding> con un elemento <xref:System.ServiceModel.Channels.TcpTransportBindingElement> che utilizza valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="21074-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
