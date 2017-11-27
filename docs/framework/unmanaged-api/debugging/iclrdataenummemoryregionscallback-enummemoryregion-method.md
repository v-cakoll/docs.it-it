---
title: Metodo ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1b1897b18a8dcbb261a5041ca8b530b7877b910
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="b0c32-102">Metodo ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="b0c32-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="b0c32-103">Chiamato da [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) per segnalare al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="b0c32-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0c32-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0c32-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0c32-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0c32-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="b0c32-106">[in] L'indirizzo iniziale dell'area di memoria che è stato possibile enumerare.</span><span class="sxs-lookup"><span data-stu-id="b0c32-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="b0c32-107">[in] Le dimensioni in byte, dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="b0c32-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0c32-108">Note</span><span class="sxs-lookup"><span data-stu-id="b0c32-108">Remarks</span></span>  
 <span data-ttu-id="b0c32-109">Il `ICLRDataEnumMemoryRegions::EnumMemoryRegions` metodo chiamerà il metodo di callback dopo ogni tentativo di enumerare un'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="b0c32-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="b0c32-110">L'enumerazione continuerà anche se questo metodo restituisce un HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="b0c32-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="b0c32-111">Le aree segnalate da questo callback possono essere duplicati o le aree di sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="b0c32-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0c32-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0c32-112">Requirements</span></span>  
 <span data-ttu-id="b0c32-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0c32-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0c32-114">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="b0c32-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b0c32-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0c32-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0c32-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0c32-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0c32-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0c32-117">See Also</span></span>  
 [<span data-ttu-id="b0c32-118">ICLRDataEnumMemoryRegionsCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b0c32-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
