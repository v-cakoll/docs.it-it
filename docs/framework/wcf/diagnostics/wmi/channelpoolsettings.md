---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 8900af77d0d385bb68b4b85e1d15be57bb7a8d14
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963976"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="328f3-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="328f3-102">ChannelPoolSettings</span></span>
<span data-ttu-id="328f3-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="328f3-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="328f3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="328f3-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="328f3-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="328f3-105">Methods</span></span>  
 <span data-ttu-id="328f3-106">La classe ChannelPoolSettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="328f3-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="328f3-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="328f3-107">Properties</span></span>  
 <span data-ttu-id="328f3-108">La classe ChannelPoolSettings dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="328f3-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="328f3-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="328f3-109">IdleTimeout</span></span>  
 <span data-ttu-id="328f3-110">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="328f3-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="328f3-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="328f3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="328f3-112">Periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="328f3-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="328f3-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="328f3-113">LeaseTimeout</span></span>  
 <span data-ttu-id="328f3-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="328f3-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="328f3-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="328f3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="328f3-116">Limite massimo di tempo per il completamento dell'operazione di lease prima del timeout.</span><span class="sxs-lookup"><span data-stu-id="328f3-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="328f3-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="328f3-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="328f3-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="328f3-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="328f3-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="328f3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="328f3-120">Numero massimo di canali in uscita per ogni endpoint.</span><span class="sxs-lookup"><span data-stu-id="328f3-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="328f3-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="328f3-121">Requirements</span></span>  
  
|<span data-ttu-id="328f3-122">MOF</span><span class="sxs-lookup"><span data-stu-id="328f3-122">MOF</span></span>|<span data-ttu-id="328f3-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="328f3-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="328f3-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="328f3-124">Namespace</span></span>|<span data-ttu-id="328f3-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="328f3-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="328f3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="328f3-126">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
