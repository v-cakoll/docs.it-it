---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: d763be92243768bce9fdaefcd3e3575effac464b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200483"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="05f97-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="05f97-102">ChannelPoolSettings</span></span>
<span data-ttu-id="05f97-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="05f97-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05f97-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05f97-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="05f97-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="05f97-105">Methods</span></span>  
 <span data-ttu-id="05f97-106">La classe ChannelPoolSettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="05f97-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="05f97-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="05f97-107">Properties</span></span>  
 <span data-ttu-id="05f97-108">La classe ChannelPoolSettings dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="05f97-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="05f97-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="05f97-109">IdleTimeout</span></span>  
 <span data-ttu-id="05f97-110">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="05f97-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="05f97-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="05f97-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05f97-112">Periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="05f97-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="05f97-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="05f97-113">LeaseTimeout</span></span>  
 <span data-ttu-id="05f97-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="05f97-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="05f97-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="05f97-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05f97-116">Limite massimo di tempo per il completamento dell'operazione di lease prima del timeout.</span><span class="sxs-lookup"><span data-stu-id="05f97-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="05f97-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="05f97-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="05f97-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="05f97-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="05f97-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="05f97-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05f97-120">Numero massimo di canali in uscita per ogni endpoint.</span><span class="sxs-lookup"><span data-stu-id="05f97-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05f97-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="05f97-121">Requirements</span></span>  
  
|<span data-ttu-id="05f97-122">MOF</span><span class="sxs-lookup"><span data-stu-id="05f97-122">MOF</span></span>|<span data-ttu-id="05f97-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="05f97-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="05f97-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="05f97-124">Namespace</span></span>|<span data-ttu-id="05f97-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="05f97-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05f97-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05f97-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
