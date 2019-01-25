---
title: Interfaccia ICLRDataEnumMemoryRegionsCallback
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0e7ce243658a8c8a8404ff9079ed1395e56486f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604150"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="165b4-102">Interfaccia ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="165b4-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="165b4-103">Fornisce un metodo di callback [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) per segnalare al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="165b4-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="165b4-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="165b4-104">Methods</span></span>  
  
|<span data-ttu-id="165b4-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="165b4-105">Method</span></span>|<span data-ttu-id="165b4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="165b4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="165b4-107">Metodo EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="165b4-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="165b4-108">Chiamato da `ICLRDataEnumMemoryRegions::EnumMemoryRegions` per segnalare al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="165b4-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="165b4-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="165b4-109">Requirements</span></span>  
 <span data-ttu-id="165b4-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="165b4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="165b4-111">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="165b4-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="165b4-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="165b4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="165b4-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="165b4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="165b4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="165b4-114">See also</span></span>
- [<span data-ttu-id="165b4-115">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="165b4-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
