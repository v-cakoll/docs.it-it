---
title: Classe Channel
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 3fbf398cca7ae9adbbecb9439bf3cbd32eb03969
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668392"
---
# <a name="channel-class"></a><span data-ttu-id="ad14d-102">Classe Channel</span><span class="sxs-lookup"><span data-stu-id="ad14d-102">Channel class</span></span>
<span data-ttu-id="ad14d-103">Canale</span><span class="sxs-lookup"><span data-stu-id="ad14d-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad14d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad14d-104">Syntax</span></span>  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ad14d-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ad14d-105">Methods</span></span>  
 <span data-ttu-id="ad14d-106">La classe Channel non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="ad14d-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ad14d-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ad14d-107">Properties</span></span>  
 <span data-ttu-id="ad14d-108">La classe Channel presenta le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="ad14d-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="ad14d-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="ad14d-109">LocalAddress</span></span>  
 <span data-ttu-id="ad14d-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ad14d-110">Data type: string</span></span>  
  
 <span data-ttu-id="ad14d-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ad14d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad14d-112">Endpoint locale del canale.</span><span class="sxs-lookup"><span data-stu-id="ad14d-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="ad14d-113">ref</span><span class="sxs-lookup"><span data-stu-id="ad14d-113">ref</span></span>  
 <span data-ttu-id="ad14d-114">Tipo di dati: Endpoint</span><span class="sxs-lookup"><span data-stu-id="ad14d-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="ad14d-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ad14d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad14d-116">Riferimento all'endpoint a cui si connette il canale.</span><span class="sxs-lookup"><span data-stu-id="ad14d-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="ad14d-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="ad14d-117">RemoteAddress</span></span>  
 <span data-ttu-id="ad14d-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ad14d-118">Data type: string</span></span>  
  
 <span data-ttu-id="ad14d-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ad14d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad14d-120">Indirizzo remoto associato al canale.</span><span class="sxs-lookup"><span data-stu-id="ad14d-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="ad14d-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="ad14d-121">SessionId</span></span>  
 <span data-ttu-id="ad14d-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ad14d-122">Data type: string</span></span>  
  
 <span data-ttu-id="ad14d-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ad14d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad14d-124">ID della sessione corrente, se presente.</span><span class="sxs-lookup"><span data-stu-id="ad14d-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="ad14d-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="ad14d-125">Type</span></span>  
 <span data-ttu-id="ad14d-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ad14d-126">Data type: string</span></span>  
  
 <span data-ttu-id="ad14d-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ad14d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad14d-128">Tipo del canale.</span><span class="sxs-lookup"><span data-stu-id="ad14d-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad14d-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad14d-129">Requirements</span></span>  
  
|<span data-ttu-id="ad14d-130">MOF</span><span class="sxs-lookup"><span data-stu-id="ad14d-130">MOF</span></span>|<span data-ttu-id="ad14d-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ad14d-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ad14d-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="ad14d-132">Namespace</span></span>|<span data-ttu-id="ad14d-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ad14d-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad14d-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad14d-134">See also</span></span>
- <xref:System.ServiceModel.Channels.ChannelBase>
