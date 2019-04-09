---
title: Interfaccia ICorPublishProcess
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08dfa3ddbfd9cffdb0cb88d0325e5703a854668a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182962"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="83107-102">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="83107-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="83107-103">Fornisce metodi che accedono alle informazioni da visualizzare su un processo.</span><span class="sxs-lookup"><span data-stu-id="83107-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83107-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="83107-104">Methods</span></span>  
  
|<span data-ttu-id="83107-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="83107-105">Method</span></span>|<span data-ttu-id="83107-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83107-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83107-107">Metodo EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="83107-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="83107-108">Ottiene un' [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) istanza che contiene i domini applicazione nel processo di cui fa riferimento questo `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="83107-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="83107-109">Metodo GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="83107-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="83107-110">Ottiene il percorso completo del file eseguibile per il processo a cui fa riferimento `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="83107-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="83107-111">Metodo GetProcessID</span><span class="sxs-lookup"><span data-stu-id="83107-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="83107-112">Ottiene l'identificatore del sistema operativo per il processo a cui fa riferimento `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="83107-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="83107-113">Metodo IsManaged</span><span class="sxs-lookup"><span data-stu-id="83107-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="83107-114">Ottiene un valore che indica se il processo fa riferimento questo `ICorPublishProcess` è noto per essere in esecuzione il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="83107-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="83107-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83107-115">Requirements</span></span>  
 <span data-ttu-id="83107-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83107-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83107-117">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="83107-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="83107-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83107-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="83107-119">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="83107-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="83107-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83107-120">See also</span></span>

- [<span data-ttu-id="83107-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="83107-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="83107-122">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="83107-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
