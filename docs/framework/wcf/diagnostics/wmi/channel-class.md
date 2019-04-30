---
title: Classe Channel
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: f60a3946617b0994db1ba9e9ddf43be863be81f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964082"
---
# <a name="channel-class"></a><span data-ttu-id="8bd34-102">Classe Channel</span><span class="sxs-lookup"><span data-stu-id="8bd34-102">Channel class</span></span>
<span data-ttu-id="8bd34-103">Canale</span><span class="sxs-lookup"><span data-stu-id="8bd34-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bd34-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8bd34-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="8bd34-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="8bd34-105">Methods</span></span>  
 <span data-ttu-id="8bd34-106">La classe Channel non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="8bd34-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8bd34-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8bd34-107">Properties</span></span>  
 <span data-ttu-id="8bd34-108">La classe Channel presenta le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="8bd34-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="8bd34-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="8bd34-109">LocalAddress</span></span>  
 <span data-ttu-id="8bd34-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="8bd34-110">Data type: string</span></span>  
  
 <span data-ttu-id="8bd34-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8bd34-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8bd34-112">Endpoint locale del canale.</span><span class="sxs-lookup"><span data-stu-id="8bd34-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="8bd34-113">ref</span><span class="sxs-lookup"><span data-stu-id="8bd34-113">ref</span></span>  
 <span data-ttu-id="8bd34-114">Tipo di dati: Endpoint</span><span class="sxs-lookup"><span data-stu-id="8bd34-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="8bd34-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8bd34-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8bd34-116">Riferimento all'endpoint a cui si connette il canale.</span><span class="sxs-lookup"><span data-stu-id="8bd34-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="8bd34-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="8bd34-117">RemoteAddress</span></span>  
 <span data-ttu-id="8bd34-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="8bd34-118">Data type: string</span></span>  
  
 <span data-ttu-id="8bd34-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8bd34-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8bd34-120">Indirizzo remoto associato al canale.</span><span class="sxs-lookup"><span data-stu-id="8bd34-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="8bd34-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="8bd34-121">SessionId</span></span>  
 <span data-ttu-id="8bd34-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="8bd34-122">Data type: string</span></span>  
  
 <span data-ttu-id="8bd34-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8bd34-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8bd34-124">ID della sessione corrente, se presente.</span><span class="sxs-lookup"><span data-stu-id="8bd34-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="8bd34-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="8bd34-125">Type</span></span>  
 <span data-ttu-id="8bd34-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="8bd34-126">Data type: string</span></span>  
  
 <span data-ttu-id="8bd34-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8bd34-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8bd34-128">Tipo del canale.</span><span class="sxs-lookup"><span data-stu-id="8bd34-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bd34-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8bd34-129">Requirements</span></span>  
  
|<span data-ttu-id="8bd34-130">MOF</span><span class="sxs-lookup"><span data-stu-id="8bd34-130">MOF</span></span>|<span data-ttu-id="8bd34-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8bd34-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8bd34-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="8bd34-132">Namespace</span></span>|<span data-ttu-id="8bd34-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8bd34-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8bd34-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bd34-134">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelBase>
