---
title: Associazioni WS-MetadataExchange
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8d305f3bf34b3b14da566fa792552e24e695ef33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="17440-102">Associazioni WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="17440-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="17440-103">In questo argomento vengono illustrate le modalità di costruzione delle associazioni predefinite per lo scambio di metadati per i vari trasporti.</span><span class="sxs-lookup"><span data-stu-id="17440-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="17440-104">Associazioni predefinite</span><span class="sxs-lookup"><span data-stu-id="17440-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="17440-105">Nome associazione predefinita</span><span class="sxs-lookup"><span data-stu-id="17440-105">Default Binding Name</span></span>|<span data-ttu-id="17440-106">Modalità di costruzione dell'associazione</span><span class="sxs-lookup"><span data-stu-id="17440-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="17440-107">MexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="17440-107">MexHttpBinding</span></span>|<span data-ttu-id="17440-108">Una classe <xref:System.ServiceModel.WSHttpBinding> con protezione a livello di trasporto attivata.</span><span class="sxs-lookup"><span data-stu-id="17440-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="17440-109">MexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="17440-109">MexHttpsBinding</span></span>|<span data-ttu-id="17440-110">Una classe <xref:System.ServiceModel.WSHttpBinding> che supporta la protezione a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="17440-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="17440-111">MexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="17440-111">MexNamedPipeBinding</span></span>|<span data-ttu-id="17440-112">Una classe <xref:System.ServiceModel.Channels.CustomBinding> con un elemento <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> che utilizza valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="17440-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="17440-113">MexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="17440-113">MexTcpBinding</span></span>|<span data-ttu-id="17440-114">Una classe <xref:System.ServiceModel.Channels.CustomBinding> con un elemento <xref:System.ServiceModel.Channels.TcpTransportBindingElement> che utilizza valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="17440-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
