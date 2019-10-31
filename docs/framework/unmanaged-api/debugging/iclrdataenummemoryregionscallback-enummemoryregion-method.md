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
ms.openlocfilehash: 2ebe7ef37fb072e3688cc4dcfa5ed89832e886e9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122942"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="e5725-102">Metodo ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="e5725-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="e5725-103">Chiamata eseguita da [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) per segnalare al debugger il risultato di un tentativo di enumerare un'area di memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="e5725-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5725-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5725-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5725-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5725-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="e5725-106">in Indirizzo iniziale dell'area di memoria che deve essere enumerata.</span><span class="sxs-lookup"><span data-stu-id="e5725-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="e5725-107">in Dimensione, in byte, dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="e5725-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5725-108">Note</span><span class="sxs-lookup"><span data-stu-id="e5725-108">Remarks</span></span>  
 <span data-ttu-id="e5725-109">Il metodo `ICLRDataEnumMemoryRegions::EnumMemoryRegions` chiamerà questo metodo di callback dopo ogni tentativo di enumerazione di un'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="e5725-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="e5725-110">L'enumerazione continuerà anche se il metodo restituisce un valore HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="e5725-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="e5725-111">Le aree segnalate da questo callback possono essere duplicati o aree sovrapposte.</span><span class="sxs-lookup"><span data-stu-id="e5725-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5725-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5725-112">Requirements</span></span>  
 <span data-ttu-id="e5725-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5725-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5725-114">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="e5725-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e5725-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5725-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5725-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5725-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5725-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5725-117">See also</span></span>

- [<span data-ttu-id="e5725-118">Interfaccia ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="e5725-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
