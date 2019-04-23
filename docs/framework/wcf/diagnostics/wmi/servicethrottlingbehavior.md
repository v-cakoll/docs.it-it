---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 572e458f08c4717207667db9940296c4a957199a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59771772"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="92a9b-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="92a9b-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="92a9b-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="92a9b-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92a9b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="92a9b-104">Syntax</span></span>  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="92a9b-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="92a9b-105">Methods</span></span>  
 <span data-ttu-id="92a9b-106">La classe ServiceThrottlingBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="92a9b-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="92a9b-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="92a9b-107">Properties</span></span>  
 <span data-ttu-id="92a9b-108">La classe ServiceThrottlingBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="92a9b-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="92a9b-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="92a9b-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="92a9b-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="92a9b-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="92a9b-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="92a9b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="92a9b-112">Numero massimo di messaggi elaborati attivamente in tutti gli oggetti dispatcher in un ServiceHost.</span><span class="sxs-lookup"><span data-stu-id="92a9b-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="92a9b-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="92a9b-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="92a9b-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="92a9b-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="92a9b-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="92a9b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="92a9b-116">Numero massimo di oggetti servizio che possono essere eseguiti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="92a9b-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="92a9b-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="92a9b-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="92a9b-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="92a9b-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="92a9b-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="92a9b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="92a9b-120">Numero massimo di sessioni che un host può accettare contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="92a9b-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92a9b-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="92a9b-121">Requirements</span></span>  
  
|<span data-ttu-id="92a9b-122">MOF</span><span class="sxs-lookup"><span data-stu-id="92a9b-122">MOF</span></span>|<span data-ttu-id="92a9b-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="92a9b-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="92a9b-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="92a9b-124">Namespace</span></span>|<span data-ttu-id="92a9b-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="92a9b-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92a9b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92a9b-126">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
