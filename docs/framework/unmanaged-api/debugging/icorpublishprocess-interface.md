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
ms.openlocfilehash: 04f6a088c5bbe96e3909ba600aa8ffab937abe2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140406"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="208d8-102">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="208d8-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="208d8-103">Fornisce metodi che accedono alle informazioni da visualizzare su un processo.</span><span class="sxs-lookup"><span data-stu-id="208d8-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="208d8-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="208d8-104">Methods</span></span>  
  
|<span data-ttu-id="208d8-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="208d8-105">Method</span></span>|<span data-ttu-id="208d8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="208d8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="208d8-107">Metodo EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="208d8-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="208d8-108">Ottiene un'istanza di [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) che contiene i domini applicazione nel processo a cui fa riferimento questo `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="208d8-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="208d8-109">Metodo GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="208d8-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="208d8-110">Ottiene il percorso completo dell'eseguibile per il processo a cui fa riferimento questo `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="208d8-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="208d8-111">Metodo GetProcessID</span><span class="sxs-lookup"><span data-stu-id="208d8-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="208d8-112">Ottiene l'identificatore del sistema operativo per il processo a cui fa riferimento questo `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="208d8-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="208d8-113">Metodo IsManaged</span><span class="sxs-lookup"><span data-stu-id="208d8-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="208d8-114">Ottiene un valore che indica se il processo a cui viene fatto riferimento da questo `ICorPublishProcess` è noto per l'esecuzione di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="208d8-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="208d8-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="208d8-115">Requirements</span></span>  
 <span data-ttu-id="208d8-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="208d8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="208d8-117">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="208d8-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="208d8-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="208d8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="208d8-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="208d8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="208d8-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="208d8-120">See also</span></span>

- [<span data-ttu-id="208d8-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="208d8-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="208d8-122">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="208d8-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
