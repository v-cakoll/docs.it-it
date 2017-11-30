---
title: Metodo ICLRDataTarget2::AllocVirtual
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget2.AllocVirtual
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e61b27ae7dcda8cc5e14d9c0f72f74c8bda13169
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="697d3-102">Metodo ICLRDataTarget2::AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="697d3-102">ICLRDataTarget2::AllocVirtual Method</span></span>
<span data-ttu-id="697d3-103">Chiamato dai servizi di accesso ai dati di common language runtime (CLR) di allocazione della memoria nello spazio degli indirizzi di questo processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="697d3-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="697d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="697d3-104">Syntax</span></span>  
  
```  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="697d3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="697d3-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="697d3-106">[in] Oggetto `CLRDATA_ADDRESS` valore che specifica l'indirizzo iniziale richiesto della memoria da allocare.</span><span class="sxs-lookup"><span data-stu-id="697d3-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="697d3-107">[in] Le dimensioni in byte, della memoria da allocare.</span><span class="sxs-lookup"><span data-stu-id="697d3-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="697d3-108">[in] Flag che controllano l'allocazione di memoria.</span><span class="sxs-lookup"><span data-stu-id="697d3-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="697d3-109">Vedere Win32 `VirtualAlloc` (funzione).</span><span class="sxs-lookup"><span data-stu-id="697d3-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="697d3-110">[in] Attributi di protezione per la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="697d3-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="697d3-111">Vedere Win32 `VirtualAlloc` (funzione).</span><span class="sxs-lookup"><span data-stu-id="697d3-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="697d3-112">[out] Un puntatore a un `CLRDATA_ADDRESS` valore che specifica l'indirizzo iniziale effettivo della memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="697d3-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="697d3-113">Note</span><span class="sxs-lookup"><span data-stu-id="697d3-113">Remarks</span></span>  
 <span data-ttu-id="697d3-114">Il `AllocVirtual` metodo funge da wrapper logico per Win32 `VirtualAlloc` (funzione).</span><span class="sxs-lookup"><span data-stu-id="697d3-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="697d3-115">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="697d3-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="697d3-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="697d3-116">Requirements</span></span>  
 <span data-ttu-id="697d3-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="697d3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="697d3-118">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="697d3-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="697d3-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="697d3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="697d3-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="697d3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="697d3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="697d3-121">See Also</span></span>  
 [<span data-ttu-id="697d3-122">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="697d3-122">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="697d3-123">FreeVirtual (metodo)</span><span class="sxs-lookup"><span data-stu-id="697d3-123">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
