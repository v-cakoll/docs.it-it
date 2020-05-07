---
title: Metodo ICLRDataTarget2::AllocVirtual
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.AllocVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type:
- apiref
ms.openlocfilehash: 20b73549d30fe210e4d44902d2f459ea9c682360
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860489"
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="15a81-102">Metodo ICLRDataTarget2::AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="15a81-102">ICLRDataTarget2::AllocVirtual Method</span></span>
<span data-ttu-id="15a81-103">Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per allocare memoria nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="15a81-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15a81-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15a81-104">Syntax</span></span>  
  
```cpp  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15a81-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="15a81-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="15a81-106">in `CLRDATA_ADDRESS` Valore che specifica l'indirizzo iniziale richiesto della memoria da allocare.</span><span class="sxs-lookup"><span data-stu-id="15a81-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="15a81-107">in Dimensione, in byte, della memoria da allocare.</span><span class="sxs-lookup"><span data-stu-id="15a81-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="15a81-108">in Flag che controllano l'allocazione della memoria.</span><span class="sxs-lookup"><span data-stu-id="15a81-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="15a81-109">Vedere la funzione `VirtualAlloc` Win32.</span><span class="sxs-lookup"><span data-stu-id="15a81-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="15a81-110">in Attributi di protezione per la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="15a81-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="15a81-111">Vedere la funzione `VirtualAlloc` Win32.</span><span class="sxs-lookup"><span data-stu-id="15a81-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="15a81-112">out Puntatore a un `CLRDATA_ADDRESS` valore che specifica l'indirizzo iniziale effettivo della memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="15a81-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15a81-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="15a81-113">Remarks</span></span>  
 <span data-ttu-id="15a81-114">Il `AllocVirtual` metodo funge da wrapper logico per la funzione Win32 `VirtualAlloc` .</span><span class="sxs-lookup"><span data-stu-id="15a81-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="15a81-115">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="15a81-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15a81-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="15a81-116">Requirements</span></span>  
 <span data-ttu-id="15a81-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15a81-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15a81-118">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="15a81-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="15a81-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15a81-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15a81-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15a81-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15a81-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15a81-121">See also</span></span>

- [<span data-ttu-id="15a81-122">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="15a81-122">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="15a81-123">Metodo FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="15a81-123">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)
