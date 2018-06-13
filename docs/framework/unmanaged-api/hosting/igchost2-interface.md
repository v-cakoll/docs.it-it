---
title: Interfaccia IGCHost2
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c6cbf44bd02a45b9b99d2dad63fc5bd6219c4ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437677"
---
# <a name="igchost2-interface"></a><span data-ttu-id="7edb3-102">Interfaccia IGCHost2</span><span class="sxs-lookup"><span data-stu-id="7edb3-102">IGCHost2 Interface</span></span>
<span data-ttu-id="7edb3-103">Fornisce metodi per ottenere informazioni sul sistema di garbage collection e per controllare alcuni aspetti dell'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="7edb3-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7edb3-104">Per un nuovo sviluppo, è consigliabile utilizzare il [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) invece di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7edb3-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7edb3-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="7edb3-105">Methods</span></span>  
  
|<span data-ttu-id="7edb3-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="7edb3-106">Method</span></span>|<span data-ttu-id="7edb3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7edb3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7edb3-108">Metodo SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="7edb3-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="7edb3-109">Imposta le dimensioni del segmento e la dimensione massima per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="7edb3-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="7edb3-110">Consente di generazione 0 e dei segmenti maggiori `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="7edb3-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7edb3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7edb3-111">Requirements</span></span>  
 <span data-ttu-id="7edb3-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7edb3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7edb3-113">**Intestazione:** GCHost. idl, GCHost. H</span><span class="sxs-lookup"><span data-stu-id="7edb3-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="7edb3-114">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7edb3-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7edb3-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7edb3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7edb3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7edb3-116">See Also</span></span>  
 [<span data-ttu-id="7edb3-117">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="7edb3-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="7edb3-118">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="7edb3-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="7edb3-119">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="7edb3-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
