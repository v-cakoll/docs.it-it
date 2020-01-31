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
ms.openlocfilehash: f2b2bbe8bcecf71f6d3016fb35dfbf5ba1353aea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785631"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="cda64-102">Metodo ICLRDataEnumMemoryRegions::EnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="cda64-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="cda64-103">Enumera le aree di memoria specificate.</span><span class="sxs-lookup"><span data-stu-id="cda64-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cda64-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cda64-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cda64-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cda64-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="cda64-106">in Puntatore a un'istanza di [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) che viene chiamata da questo metodo per ogni area di memoria enumerata per notificare al debugger il risultato.</span><span class="sxs-lookup"><span data-stu-id="cda64-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="cda64-107">L'enumerazione delle aree di memoria continua anche se il callback indica un errore.</span><span class="sxs-lookup"><span data-stu-id="cda64-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="cda64-108">in Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="cda64-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="cda64-109">in Valore dell'enumerazione [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) che specifica le aree di memoria da enumerare.</span><span class="sxs-lookup"><span data-stu-id="cda64-109">[in] A value of the [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cda64-110">Note</span><span class="sxs-lookup"><span data-stu-id="cda64-110">Remarks</span></span>  
 <span data-ttu-id="cda64-111">Questo metodo usa l'istanza di [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) specificata per notificare al chiamante i risultati.</span><span class="sxs-lookup"><span data-stu-id="cda64-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cda64-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="cda64-112">Requirements</span></span>  
 <span data-ttu-id="cda64-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cda64-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cda64-114">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="cda64-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="cda64-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cda64-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cda64-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cda64-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cda64-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cda64-117">See also</span></span>

- [<span data-ttu-id="cda64-118">Interfaccia ICLRDataEnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="cda64-118">ICLRDataEnumMemoryRegions Interface</span></span>](iclrdataenummemoryregions-interface.md)
