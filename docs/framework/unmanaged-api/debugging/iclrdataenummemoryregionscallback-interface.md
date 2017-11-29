---
title: Interfaccia ICLRDataEnumMemoryRegionsCallback
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataEnumMemoryRegionsCallback
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords: ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 40e51bfc176d8be6b008bc4274c0933253d7be3a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="4a51f-102">Interfaccia ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="4a51f-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="4a51f-103">Fornisce un metodo di callback per [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) per segnalare al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="4a51f-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4a51f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4a51f-104">Methods</span></span>  
  
|<span data-ttu-id="4a51f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4a51f-105">Method</span></span>|<span data-ttu-id="4a51f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a51f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4a51f-107">EnumMemoryRegion (metodo)</span><span class="sxs-lookup"><span data-stu-id="4a51f-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="4a51f-108">Chiamato da `ICLRDataEnumMemoryRegions::EnumMemoryRegions` per segnalare al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="4a51f-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a51f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a51f-109">Requirements</span></span>  
 <span data-ttu-id="4a51f-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a51f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a51f-111">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="4a51f-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="4a51f-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a51f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a51f-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a51f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a51f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a51f-114">See Also</span></span>  
 [<span data-ttu-id="4a51f-115">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4a51f-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
