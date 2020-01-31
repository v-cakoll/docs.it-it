---
title: Metodo ICLRDataTarget::SetTLSValue
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
ms.openlocfilehash: 6e6e157c7176a0f4f1ad3c585977e2cfb31c33d8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793693"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="3540d-102">Metodo ICLRDataTarget::SetTLSValue</span><span class="sxs-lookup"><span data-stu-id="3540d-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="3540d-103">Imposta un valore nell'archiviazione locale di thread (TLS) del thread specificato nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3540d-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="3540d-104">Questo metodo viene chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3540d-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3540d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3540d-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3540d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3540d-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="3540d-107">in Identificatore del sistema operativo di un thread nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3540d-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="3540d-108">in Indice della posizione.</span><span class="sxs-lookup"><span data-stu-id="3540d-108">[in] The index of the location.</span></span> <span data-ttu-id="3540d-109">Questo valore deve essere un indice valido nell'archivio locale del thread specificato.</span><span class="sxs-lookup"><span data-stu-id="3540d-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="3540d-110">in Valore `CLRDATA_ADDRESS` che specifica il valore da inserire nella posizione TLS specificata.</span><span class="sxs-lookup"><span data-stu-id="3540d-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3540d-111">Note</span><span class="sxs-lookup"><span data-stu-id="3540d-111">Remarks</span></span>  
 <span data-ttu-id="3540d-112">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="3540d-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3540d-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3540d-113">Requirements</span></span>  
 <span data-ttu-id="3540d-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3540d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3540d-115">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="3540d-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3540d-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3540d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3540d-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3540d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3540d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3540d-118">See also</span></span>

- [<span data-ttu-id="3540d-119">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="3540d-119">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
