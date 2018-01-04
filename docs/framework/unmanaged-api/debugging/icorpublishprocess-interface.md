---
title: Interfaccia ICorPublishProcess
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess
helpviewer_keywords: ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 765be4e0ae7657d169ea561bc6a36bcf8cc11153
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="cfc64-102">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="cfc64-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="cfc64-103">Fornisce metodi che accedono alle informazioni da visualizzare su un processo.</span><span class="sxs-lookup"><span data-stu-id="cfc64-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cfc64-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="cfc64-104">Methods</span></span>  
  
|<span data-ttu-id="cfc64-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="cfc64-105">Method</span></span>|<span data-ttu-id="cfc64-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfc64-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cfc64-107">Metodo EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="cfc64-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="cfc64-108">Ottiene un [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) istanza che contiene i domini applicazione nel processo di cui fa riferimento questo `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="cfc64-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="cfc64-109">Metodo GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="cfc64-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="cfc64-110">Ottiene il percorso completo del file eseguibile per il processo a cui fa riferimento questo `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="cfc64-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="cfc64-111">Metodo GetProcessID</span><span class="sxs-lookup"><span data-stu-id="cfc64-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="cfc64-112">Ottiene l'identificatore del sistema operativo per il processo a cui fa riferimento questo `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="cfc64-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="cfc64-113">Metodo IsManaged</span><span class="sxs-lookup"><span data-stu-id="cfc64-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="cfc64-114">Ottiene un valore che indica se il processo a cui fa riferimento questo `ICorPublishProcess` è noto in esecuzione il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="cfc64-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cfc64-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cfc64-115">Requirements</span></span>  
 <span data-ttu-id="cfc64-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfc64-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfc64-117">**Intestazione:** Corpub. idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="cfc64-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="cfc64-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfc64-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfc64-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfc64-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc64-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfc64-120">See Also</span></span>  
 [<span data-ttu-id="cfc64-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="cfc64-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="cfc64-122">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="cfc64-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
