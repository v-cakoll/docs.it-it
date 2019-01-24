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
ms.openlocfilehash: 742f738ca1a147c75b976d24fa4ac8e7fa4947c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622234"
---
# <a name="igchost2-interface"></a><span data-ttu-id="ecf63-102">Interfaccia IGCHost2</span><span class="sxs-lookup"><span data-stu-id="ecf63-102">IGCHost2 Interface</span></span>
<span data-ttu-id="ecf63-103">Fornisce metodi di recupero di informazioni sul sistema di garbage collection e di controllo di alcuni aspetti del processo di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ecf63-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecf63-104">Per i nuovi sviluppi, è consigliabile usare la [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) invece dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ecf63-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ecf63-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ecf63-105">Methods</span></span>  
  
|<span data-ttu-id="ecf63-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="ecf63-106">Method</span></span>|<span data-ttu-id="ecf63-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ecf63-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ecf63-108">Metodo SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="ecf63-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="ecf63-109">Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="ecf63-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="ecf63-110">Abilita generazione 0 e dimensioni del segmento superiori a `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="ecf63-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ecf63-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ecf63-111">Requirements</span></span>  
 <span data-ttu-id="ecf63-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecf63-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecf63-113">**Intestazione:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="ecf63-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="ecf63-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ecf63-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ecf63-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecf63-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecf63-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecf63-116">See also</span></span>
- [<span data-ttu-id="ecf63-117">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="ecf63-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ecf63-118">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="ecf63-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="ecf63-119">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ecf63-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
