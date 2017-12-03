---
title: Classe Channel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 93632d6a178c0f58143fc148a0e1eb51be94ed17
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="channel-class"></a><span data-ttu-id="9996f-102">Classe Channel</span><span class="sxs-lookup"><span data-stu-id="9996f-102">Channel class</span></span>
<span data-ttu-id="9996f-103">Canale</span><span class="sxs-lookup"><span data-stu-id="9996f-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9996f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9996f-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="9996f-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="9996f-105">Methods</span></span>  
 <span data-ttu-id="9996f-106">La classe Channel non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="9996f-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9996f-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="9996f-107">Properties</span></span>  
 <span data-ttu-id="9996f-108">La classe Channel presenta le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="9996f-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="9996f-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="9996f-109">LocalAddress</span></span>  
 <span data-ttu-id="9996f-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9996f-110">Data type: string</span></span>  
  
 <span data-ttu-id="9996f-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9996f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9996f-112">Endpoint locale del canale.</span><span class="sxs-lookup"><span data-stu-id="9996f-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="9996f-113">ref</span><span class="sxs-lookup"><span data-stu-id="9996f-113">ref</span></span>  
 <span data-ttu-id="9996f-114">Tipo di dati: endpoint</span><span class="sxs-lookup"><span data-stu-id="9996f-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="9996f-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9996f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9996f-116">Riferimento all'endpoint a cui si connette il canale.</span><span class="sxs-lookup"><span data-stu-id="9996f-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="9996f-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="9996f-117">RemoteAddress</span></span>  
 <span data-ttu-id="9996f-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9996f-118">Data type: string</span></span>  
  
 <span data-ttu-id="9996f-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9996f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9996f-120">Indirizzo remoto associato al canale.</span><span class="sxs-lookup"><span data-stu-id="9996f-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="9996f-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="9996f-121">SessionId</span></span>  
 <span data-ttu-id="9996f-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9996f-122">Data type: string</span></span>  
  
 <span data-ttu-id="9996f-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9996f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9996f-124">ID della sessione corrente, se presente.</span><span class="sxs-lookup"><span data-stu-id="9996f-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="9996f-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="9996f-125">Type</span></span>  
 <span data-ttu-id="9996f-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9996f-126">Data type: string</span></span>  
  
 <span data-ttu-id="9996f-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9996f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9996f-128">Tipo del canale.</span><span class="sxs-lookup"><span data-stu-id="9996f-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9996f-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9996f-129">Requirements</span></span>  
  
|<span data-ttu-id="9996f-130">MOF</span><span class="sxs-lookup"><span data-stu-id="9996f-130">MOF</span></span>|<span data-ttu-id="9996f-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9996f-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9996f-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="9996f-132">Namespace</span></span>|<span data-ttu-id="9996f-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9996f-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9996f-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9996f-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
