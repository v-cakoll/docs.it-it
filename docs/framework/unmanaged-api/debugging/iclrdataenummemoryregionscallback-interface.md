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
ms.openlocfilehash: 0a0af0c86bc44a4968119e1afd2a84e17e941601
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405499"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="2ac04-102">Interfaccia ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="2ac04-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="2ac04-103">Fornisce un metodo di callback per [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) per segnalare al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="2ac04-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ac04-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="2ac04-104">Methods</span></span>  
  
|<span data-ttu-id="2ac04-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="2ac04-105">Method</span></span>|<span data-ttu-id="2ac04-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ac04-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ac04-107">Metodo EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="2ac04-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="2ac04-108">Chiamato da `ICLRDataEnumMemoryRegions::EnumMemoryRegions` per segnalare al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="2ac04-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2ac04-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ac04-109">Requirements</span></span>  
 <span data-ttu-id="2ac04-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ac04-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ac04-111">**Intestazione:** Clrdata. idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="2ac04-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2ac04-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2ac04-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ac04-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ac04-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac04-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ac04-114">See Also</span></span>  
 [<span data-ttu-id="2ac04-115">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2ac04-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
