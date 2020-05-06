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
ms.openlocfilehash: e4fa0a3745200d39a468292e9520b1aeb0e9f1b2
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860676"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="703ae-102">Metodo ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="703ae-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="703ae-103">Chiamata eseguita da [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) per segnalare al debugger il risultato di un tentativo di enumerare un'area di memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="703ae-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="703ae-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="703ae-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="703ae-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="703ae-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="703ae-106">in Indirizzo iniziale dell'area di memoria che deve essere enumerata.</span><span class="sxs-lookup"><span data-stu-id="703ae-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="703ae-107">in Dimensione, in byte, dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="703ae-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="703ae-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="703ae-108">Remarks</span></span>  
 <span data-ttu-id="703ae-109">Il `ICLRDataEnumMemoryRegions::EnumMemoryRegions` metodo chiamerà questo metodo di callback dopo ogni tentativo di enumerazione di un'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="703ae-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="703ae-110">L'enumerazione continuerà anche se il metodo restituisce un valore HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="703ae-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="703ae-111">Le aree segnalate da questo callback possono essere duplicati o aree sovrapposte.</span><span class="sxs-lookup"><span data-stu-id="703ae-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="703ae-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="703ae-112">Requirements</span></span>  
 <span data-ttu-id="703ae-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="703ae-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="703ae-114">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="703ae-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="703ae-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="703ae-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="703ae-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="703ae-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="703ae-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="703ae-117">See also</span></span>

- [<span data-ttu-id="703ae-118">Interfaccia ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="703ae-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](iclrdataenummemoryregionscallback-interface.md)
