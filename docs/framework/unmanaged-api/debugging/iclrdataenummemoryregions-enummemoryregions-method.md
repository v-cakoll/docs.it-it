---
title: Metodo ICLRDataEnumMemoryRegions::EnumMemoryRegions
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
ms.openlocfilehash: e6cdc924df126e56d2e7c8c9cb8762ee88712fcc
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860692"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="9b133-102">Metodo ICLRDataEnumMemoryRegions::EnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="9b133-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="9b133-103">Enumera le aree di memoria specificate.</span><span class="sxs-lookup"><span data-stu-id="9b133-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b133-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b133-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b133-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9b133-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="9b133-106">in Puntatore a un'istanza di [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) che viene chiamata da questo metodo per ogni area di memoria enumerata per notificare al debugger il risultato.</span><span class="sxs-lookup"><span data-stu-id="9b133-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="9b133-107">L'enumerazione delle aree di memoria continua anche se il callback indica un errore.</span><span class="sxs-lookup"><span data-stu-id="9b133-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="9b133-108">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="9b133-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="9b133-109">in Valore dell'enumerazione [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) che specifica le aree di memoria da enumerare.</span><span class="sxs-lookup"><span data-stu-id="9b133-109">[in] A value of the [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b133-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9b133-110">Remarks</span></span>  
 <span data-ttu-id="9b133-111">Questo metodo usa l'istanza di [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) specificata per notificare al chiamante i risultati.</span><span class="sxs-lookup"><span data-stu-id="9b133-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b133-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9b133-112">Requirements</span></span>  
 <span data-ttu-id="9b133-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b133-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b133-114">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="9b133-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="9b133-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b133-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b133-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b133-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b133-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b133-117">See also</span></span>

- [<span data-ttu-id="9b133-118">Interfaccia ICLRDataEnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="9b133-118">ICLRDataEnumMemoryRegions Interface</span></span>](iclrdataenummemoryregions-interface.md)
