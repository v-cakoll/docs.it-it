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
ms.openlocfilehash: 43c16415c91521194e0d88be84dd176c3fdadad1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134842"
---
# <a name="igchost2-interface"></a><span data-ttu-id="33453-102">Interfaccia IGCHost2</span><span class="sxs-lookup"><span data-stu-id="33453-102">IGCHost2 Interface</span></span>
<span data-ttu-id="33453-103">Fornisce metodi per ottenere informazioni sul sistema Garbage Collection e per controllare alcuni aspetti di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="33453-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33453-104">Per un nuovo sviluppo, è consigliabile usare invece l'interfaccia [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="33453-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33453-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="33453-105">Methods</span></span>  
  
|<span data-ttu-id="33453-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="33453-106">Method</span></span>|<span data-ttu-id="33453-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33453-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33453-108">Metodo SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="33453-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="33453-109">Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="33453-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="33453-110">Abilita la generazione 0 e le dimensioni dei segmenti maggiori di `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="33453-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33453-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33453-111">Requirements</span></span>  
 <span data-ttu-id="33453-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33453-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33453-113">**Intestazione:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="33453-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="33453-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="33453-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33453-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33453-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33453-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33453-116">See also</span></span>

- [<span data-ttu-id="33453-117">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="33453-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="33453-118">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="33453-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="33453-119">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="33453-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
