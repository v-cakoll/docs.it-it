---
title: Metodo ICLRDataTarget2::FreeVirtual
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
ms.openlocfilehash: c084a3fcbbc02504124a511c6e136be32f408d21
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73112321"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="017c0-102">Metodo ICLRDataTarget2::FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="017c0-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="017c0-103">Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per liberare memoria allocata in precedenza nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="017c0-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="017c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="017c0-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="017c0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="017c0-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="017c0-106">in Valore `CLRDATA_ADDRESS` che specifica l'indirizzo iniziale della memoria da liberare.</span><span class="sxs-lookup"><span data-stu-id="017c0-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="017c0-107">in Dimensione, in byte, della memoria da liberare.</span><span class="sxs-lookup"><span data-stu-id="017c0-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="017c0-108">in Flag che controllano la liberazione della memoria.</span><span class="sxs-lookup"><span data-stu-id="017c0-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="017c0-109">Vedere la funzione Win32 `VirtualFree`.</span><span class="sxs-lookup"><span data-stu-id="017c0-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="017c0-110">Note</span><span class="sxs-lookup"><span data-stu-id="017c0-110">Remarks</span></span>  
 <span data-ttu-id="017c0-111">Il metodo `FreeVirtual` funge da wrapper logico per la funzione di `VirtualFree` Win32.</span><span class="sxs-lookup"><span data-stu-id="017c0-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="017c0-112">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="017c0-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="017c0-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="017c0-113">Requirements</span></span>  
 <span data-ttu-id="017c0-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="017c0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="017c0-115">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="017c0-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="017c0-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="017c0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="017c0-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="017c0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="017c0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="017c0-118">See also</span></span>

- [<span data-ttu-id="017c0-119">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="017c0-119">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="017c0-120">Metodo AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="017c0-120">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
