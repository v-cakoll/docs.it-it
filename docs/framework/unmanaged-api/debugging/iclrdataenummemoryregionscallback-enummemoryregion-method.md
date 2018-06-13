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
ms.openlocfilehash: d0ed92cbf5a859b9d5b7b8eddefda3ad34a98f27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404050"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="60a5b-102">Metodo ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="60a5b-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="60a5b-103">Chiamato da [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) per segnalare al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="60a5b-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60a5b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60a5b-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="60a5b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="60a5b-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="60a5b-106">[in] L'indirizzo iniziale dell'area di memoria che è stato possibile enumerare.</span><span class="sxs-lookup"><span data-stu-id="60a5b-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="60a5b-107">[in] Le dimensioni in byte, dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="60a5b-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60a5b-108">Note</span><span class="sxs-lookup"><span data-stu-id="60a5b-108">Remarks</span></span>  
 <span data-ttu-id="60a5b-109">Il `ICLRDataEnumMemoryRegions::EnumMemoryRegions` metodo chiamerà il metodo di callback dopo ogni tentativo di enumerare un'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="60a5b-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="60a5b-110">L'enumerazione continuerà anche se questo metodo restituisce un HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="60a5b-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="60a5b-111">Le aree segnalate da questo callback possono essere duplicati o le aree di sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="60a5b-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60a5b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="60a5b-112">Requirements</span></span>  
 <span data-ttu-id="60a5b-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60a5b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60a5b-114">**Intestazione:** Clrdata. idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="60a5b-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="60a5b-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="60a5b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60a5b-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60a5b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60a5b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60a5b-117">See Also</span></span>  
 [<span data-ttu-id="60a5b-118">Interfaccia ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="60a5b-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
