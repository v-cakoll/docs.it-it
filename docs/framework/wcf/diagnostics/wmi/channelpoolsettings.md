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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0a56616e97526b2d410d18d97dc1391c6fc32cc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="channelpoolsettings"></a><span data-ttu-id="ab487-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="ab487-102">ChannelPoolSettings</span></span>
<span data-ttu-id="ab487-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="ab487-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab487-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab487-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ab487-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ab487-105">Methods</span></span>  
 <span data-ttu-id="ab487-106">La classe ChannelPoolSettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="ab487-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ab487-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ab487-107">Properties</span></span>  
 <span data-ttu-id="ab487-108">La classe ChannelPoolSettings dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab487-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="ab487-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="ab487-109">IdleTimeout</span></span>  
 <span data-ttu-id="ab487-110">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="ab487-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="ab487-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ab487-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ab487-112">Periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="ab487-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="ab487-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="ab487-113">LeaseTimeout</span></span>  
 <span data-ttu-id="ab487-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="ab487-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="ab487-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ab487-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ab487-116">Limite massimo di tempo per il completamento dell'operazione di lease prima del timeout.</span><span class="sxs-lookup"><span data-stu-id="ab487-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="ab487-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="ab487-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="ab487-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="ab487-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="ab487-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ab487-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ab487-120">Numero massimo di canali in uscita per ogni endpoint.</span><span class="sxs-lookup"><span data-stu-id="ab487-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab487-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ab487-121">Requirements</span></span>  
  
|<span data-ttu-id="ab487-122">MOF</span><span class="sxs-lookup"><span data-stu-id="ab487-122">MOF</span></span>|<span data-ttu-id="ab487-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ab487-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ab487-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="ab487-124">Namespace</span></span>|<span data-ttu-id="ab487-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ab487-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab487-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab487-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
