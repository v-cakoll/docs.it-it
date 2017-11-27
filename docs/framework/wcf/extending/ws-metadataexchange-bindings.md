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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 23752cb259accb1df6093a4b1d90a2541fd771d4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="d3e87-102">Associazioni WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="d3e87-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="d3e87-103">In questo argomento vengono illustrate le modalità di costruzione delle associazioni predefinite per lo scambio di metadati per i vari trasporti.</span><span class="sxs-lookup"><span data-stu-id="d3e87-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="d3e87-104">Associazioni predefinite</span><span class="sxs-lookup"><span data-stu-id="d3e87-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="d3e87-105">Nome associazione predefinita</span><span class="sxs-lookup"><span data-stu-id="d3e87-105">Default Binding Name</span></span>|<span data-ttu-id="d3e87-106">Modalità di costruzione dell'associazione</span><span class="sxs-lookup"><span data-stu-id="d3e87-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="d3e87-107">MexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d3e87-107">MexHttpBinding</span></span>|<span data-ttu-id="d3e87-108">Una classe <xref:System.ServiceModel.WSHttpBinding> con protezione a livello di trasporto attivata.</span><span class="sxs-lookup"><span data-stu-id="d3e87-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="d3e87-109">MexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="d3e87-109">MexHttpsBinding</span></span>|<span data-ttu-id="d3e87-110">Una classe <xref:System.ServiceModel.WSHttpBinding> che supporta la protezione a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d3e87-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="d3e87-111">MexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="d3e87-111">MexNamedPipeBinding</span></span>|<span data-ttu-id="d3e87-112">Una classe <xref:System.ServiceModel.Channels.CustomBinding> con un elemento <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> che utilizza valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="d3e87-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="d3e87-113">MexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="d3e87-113">MexTcpBinding</span></span>|<span data-ttu-id="d3e87-114">Una classe <xref:System.ServiceModel.Channels.CustomBinding> con un elemento <xref:System.ServiceModel.Channels.TcpTransportBindingElement> che utilizza valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="d3e87-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
