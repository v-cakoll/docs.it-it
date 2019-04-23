---
title: Metodo ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85b1c5455cb2008a352461d6b506e43fcef48d17
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130923"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="307c1-102">Metodo ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="307c1-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="307c1-103">Chiamata eseguita dal [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) per segnalare al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="307c1-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="307c1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="307c1-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="307c1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="307c1-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="307c1-106">[in] Indirizzo iniziale dell'area di memoria che è stata da enumerare.</span><span class="sxs-lookup"><span data-stu-id="307c1-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="307c1-107">[in] Le dimensioni, in byte, dell'area della memoria.</span><span class="sxs-lookup"><span data-stu-id="307c1-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="307c1-108">Note</span><span class="sxs-lookup"><span data-stu-id="307c1-108">Remarks</span></span>  
 <span data-ttu-id="307c1-109">Il `ICLRDataEnumMemoryRegions::EnumMemoryRegions` metodo chiamerà il metodo di callback dopo ogni tentativo di enumerare un'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="307c1-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="307c1-110">L'enumerazione continuerà anche se questo metodo restituisce un HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="307c1-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="307c1-111">Le aree segnalate da questo callback possono essere duplicati o le aree di sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="307c1-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="307c1-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="307c1-112">Requirements</span></span>  
 <span data-ttu-id="307c1-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="307c1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="307c1-114">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="307c1-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="307c1-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="307c1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="307c1-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="307c1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="307c1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="307c1-117">See also</span></span>

- [<span data-ttu-id="307c1-118">Interfaccia ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="307c1-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
