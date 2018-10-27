---
title: Classe Channel
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 108d5f8e3cd092863dbd48e2bb9d180798b091a4
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50047371"
---
# <a name="channel-class"></a><span data-ttu-id="4151c-102">Classe Channel</span><span class="sxs-lookup"><span data-stu-id="4151c-102">Channel class</span></span>
<span data-ttu-id="4151c-103">Canale</span><span class="sxs-lookup"><span data-stu-id="4151c-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4151c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4151c-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="4151c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="4151c-105">Methods</span></span>  
 <span data-ttu-id="4151c-106">La classe Channel non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="4151c-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4151c-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4151c-107">Properties</span></span>  
 <span data-ttu-id="4151c-108">La classe Channel presenta le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="4151c-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="4151c-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="4151c-109">LocalAddress</span></span>  
 <span data-ttu-id="4151c-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4151c-110">Data type: string</span></span>  
  
 <span data-ttu-id="4151c-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4151c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4151c-112">Endpoint locale del canale.</span><span class="sxs-lookup"><span data-stu-id="4151c-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="4151c-113">ref</span><span class="sxs-lookup"><span data-stu-id="4151c-113">ref</span></span>  
 <span data-ttu-id="4151c-114">Tipo di dati: endpoint</span><span class="sxs-lookup"><span data-stu-id="4151c-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="4151c-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4151c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4151c-116">Riferimento all'endpoint a cui si connette il canale.</span><span class="sxs-lookup"><span data-stu-id="4151c-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="4151c-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="4151c-117">RemoteAddress</span></span>  
 <span data-ttu-id="4151c-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4151c-118">Data type: string</span></span>  
  
 <span data-ttu-id="4151c-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4151c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4151c-120">Indirizzo remoto associato al canale.</span><span class="sxs-lookup"><span data-stu-id="4151c-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="4151c-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="4151c-121">SessionId</span></span>  
 <span data-ttu-id="4151c-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4151c-122">Data type: string</span></span>  
  
 <span data-ttu-id="4151c-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4151c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4151c-124">ID della sessione corrente, se presente.</span><span class="sxs-lookup"><span data-stu-id="4151c-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="4151c-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="4151c-125">Type</span></span>  
 <span data-ttu-id="4151c-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4151c-126">Data type: string</span></span>  
  
 <span data-ttu-id="4151c-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4151c-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4151c-128">Tipo del canale.</span><span class="sxs-lookup"><span data-stu-id="4151c-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4151c-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4151c-129">Requirements</span></span>  
  
|<span data-ttu-id="4151c-130">MOF</span><span class="sxs-lookup"><span data-stu-id="4151c-130">MOF</span></span>|<span data-ttu-id="4151c-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4151c-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4151c-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="4151c-132">Namespace</span></span>|<span data-ttu-id="4151c-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4151c-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4151c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4151c-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
