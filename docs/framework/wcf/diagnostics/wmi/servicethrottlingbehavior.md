---
title: ServiceThrottlingBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 779aabf5ec9b1bca7151eaf781c6dd6f2631b58f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="fd9b6-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="fd9b6-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="fd9b6-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="fd9b6-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd9b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd9b6-104">Syntax</span></span>  
  
```  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fd9b6-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="fd9b6-105">Methods</span></span>  
 <span data-ttu-id="fd9b6-106">La classe ServiceThrottlingBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fd9b6-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="fd9b6-107">Properties</span></span>  
 <span data-ttu-id="fd9b6-108">La classe ServiceThrottlingBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd9b6-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="fd9b6-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="fd9b6-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="fd9b6-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="fd9b6-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="fd9b6-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="fd9b6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd9b6-112">Numero massimo di messaggi elaborati attivamente in tutti gli oggetti dispatcher in un ServiceHost.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="fd9b6-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="fd9b6-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="fd9b6-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="fd9b6-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="fd9b6-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="fd9b6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd9b6-116">Numero massimo di oggetti servizio che possono essere eseguiti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="fd9b6-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="fd9b6-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="fd9b6-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="fd9b6-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="fd9b6-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="fd9b6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd9b6-120">Numero massimo di sessioni che un host può accettare contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd9b6-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd9b6-121">Requirements</span></span>  
  
|<span data-ttu-id="fd9b6-122">MOF</span><span class="sxs-lookup"><span data-stu-id="fd9b6-122">MOF</span></span>|<span data-ttu-id="fd9b6-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fd9b6-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="fd9b6-124">Namespace</span></span>|<span data-ttu-id="fd9b6-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fd9b6-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd9b6-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd9b6-126">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
