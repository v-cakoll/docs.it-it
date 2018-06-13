---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 48b41d2f3f45cd9c590f87151253450962b994de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485297"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="748ac-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="748ac-102">ChannelPoolSettings</span></span>
<span data-ttu-id="748ac-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="748ac-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="748ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="748ac-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="748ac-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="748ac-105">Methods</span></span>  
 <span data-ttu-id="748ac-106">La classe ChannelPoolSettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="748ac-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="748ac-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="748ac-107">Properties</span></span>  
 <span data-ttu-id="748ac-108">La classe ChannelPoolSettings dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="748ac-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="748ac-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="748ac-109">IdleTimeout</span></span>  
 <span data-ttu-id="748ac-110">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="748ac-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="748ac-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="748ac-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="748ac-112">Periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="748ac-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="748ac-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="748ac-113">LeaseTimeout</span></span>  
 <span data-ttu-id="748ac-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="748ac-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="748ac-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="748ac-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="748ac-116">Limite massimo di tempo per il completamento dell'operazione di lease prima del timeout.</span><span class="sxs-lookup"><span data-stu-id="748ac-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="748ac-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="748ac-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="748ac-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="748ac-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="748ac-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="748ac-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="748ac-120">Numero massimo di canali in uscita per ogni endpoint.</span><span class="sxs-lookup"><span data-stu-id="748ac-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="748ac-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="748ac-121">Requirements</span></span>  
  
|<span data-ttu-id="748ac-122">MOF</span><span class="sxs-lookup"><span data-stu-id="748ac-122">MOF</span></span>|<span data-ttu-id="748ac-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="748ac-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="748ac-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="748ac-124">Namespace</span></span>|<span data-ttu-id="748ac-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="748ac-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="748ac-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="748ac-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
