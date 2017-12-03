---
title: ChannelPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e97e934673efbc6d0f72751c7cb1de6fba84a141
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="channelpoolsettings"></a><span data-ttu-id="fe416-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="fe416-102">ChannelPoolSettings</span></span>
<span data-ttu-id="fe416-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="fe416-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe416-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe416-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fe416-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="fe416-105">Methods</span></span>  
 <span data-ttu-id="fe416-106">La classe ChannelPoolSettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="fe416-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fe416-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="fe416-107">Properties</span></span>  
 <span data-ttu-id="fe416-108">La classe ChannelPoolSettings dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe416-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="fe416-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="fe416-109">IdleTimeout</span></span>  
 <span data-ttu-id="fe416-110">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="fe416-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="fe416-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="fe416-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe416-112">Periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="fe416-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="fe416-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="fe416-113">LeaseTimeout</span></span>  
 <span data-ttu-id="fe416-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="fe416-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="fe416-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="fe416-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe416-116">Limite massimo di tempo per il completamento dell'operazione di lease prima del timeout.</span><span class="sxs-lookup"><span data-stu-id="fe416-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="fe416-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="fe416-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="fe416-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="fe416-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="fe416-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="fe416-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe416-120">Numero massimo di canali in uscita per ogni endpoint.</span><span class="sxs-lookup"><span data-stu-id="fe416-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe416-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe416-121">Requirements</span></span>  
  
|<span data-ttu-id="fe416-122">MOF</span><span class="sxs-lookup"><span data-stu-id="fe416-122">MOF</span></span>|<span data-ttu-id="fe416-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fe416-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fe416-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="fe416-124">Namespace</span></span>|<span data-ttu-id="fe416-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fe416-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe416-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe416-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
