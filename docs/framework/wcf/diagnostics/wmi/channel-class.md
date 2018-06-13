---
title: Classe Channel
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 4b7c66560c0c136a258c527d8a681d491eb50aae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485801"
---
# <a name="channel-class"></a><span data-ttu-id="91ad0-102">Classe Channel</span><span class="sxs-lookup"><span data-stu-id="91ad0-102">Channel class</span></span>
<span data-ttu-id="91ad0-103">Canale</span><span class="sxs-lookup"><span data-stu-id="91ad0-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91ad0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91ad0-104">Syntax</span></span>  
  
```  
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="91ad0-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="91ad0-105">Methods</span></span>  
 <span data-ttu-id="91ad0-106">La classe Channel non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="91ad0-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="91ad0-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="91ad0-107">Properties</span></span>  
 <span data-ttu-id="91ad0-108">La classe Channel presenta le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="91ad0-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="91ad0-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="91ad0-109">LocalAddress</span></span>  
 <span data-ttu-id="91ad0-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="91ad0-110">Data type: string</span></span>  
  
 <span data-ttu-id="91ad0-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="91ad0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91ad0-112">Endpoint locale del canale.</span><span class="sxs-lookup"><span data-stu-id="91ad0-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="91ad0-113">ref</span><span class="sxs-lookup"><span data-stu-id="91ad0-113">ref</span></span>  
 <span data-ttu-id="91ad0-114">Tipo di dati: endpoint</span><span class="sxs-lookup"><span data-stu-id="91ad0-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="91ad0-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="91ad0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91ad0-116">Riferimento all'endpoint a cui si connette il canale.</span><span class="sxs-lookup"><span data-stu-id="91ad0-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="91ad0-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="91ad0-117">RemoteAddress</span></span>  
 <span data-ttu-id="91ad0-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="91ad0-118">Data type: string</span></span>  
  
 <span data-ttu-id="91ad0-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="91ad0-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91ad0-120">Indirizzo remoto associato al canale.</span><span class="sxs-lookup"><span data-stu-id="91ad0-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="91ad0-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="91ad0-121">SessionId</span></span>  
 <span data-ttu-id="91ad0-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="91ad0-122">Data type: string</span></span>  
  
 <span data-ttu-id="91ad0-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="91ad0-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91ad0-124">ID della sessione corrente, se presente.</span><span class="sxs-lookup"><span data-stu-id="91ad0-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="91ad0-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="91ad0-125">Type</span></span>  
 <span data-ttu-id="91ad0-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="91ad0-126">Data type: string</span></span>  
  
 <span data-ttu-id="91ad0-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="91ad0-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91ad0-128">Tipo del canale.</span><span class="sxs-lookup"><span data-stu-id="91ad0-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91ad0-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="91ad0-129">Requirements</span></span>  
  
|<span data-ttu-id="91ad0-130">MOF</span><span class="sxs-lookup"><span data-stu-id="91ad0-130">MOF</span></span>|<span data-ttu-id="91ad0-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="91ad0-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="91ad0-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="91ad0-132">Namespace</span></span>|<span data-ttu-id="91ad0-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="91ad0-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91ad0-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91ad0-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
