---
title: Metodo ICLRDataTarget::Request
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc79277c75118b11766e66137284bd5655eed091
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405372"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="b04be-102">Metodo ICLRDataTarget::Request</span><span class="sxs-lookup"><span data-stu-id="b04be-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="b04be-103">Chiamato dai servizi di accesso ai dati di common language runtime (CLR) per richiedere un'operazione, come definito dall'implementazione.</span><span class="sxs-lookup"><span data-stu-id="b04be-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b04be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b04be-104">Syntax</span></span>  
  
```  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]   
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]   
        BYTE                *outBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b04be-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b04be-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="b04be-106">[in] Definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b04be-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="b04be-107">[in] Le dimensioni del buffer di input, viene utilizzato per la richiesta in ingresso.</span><span class="sxs-lookup"><span data-stu-id="b04be-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="b04be-108">[in] Un buffer che contiene la richiesta.</span><span class="sxs-lookup"><span data-stu-id="b04be-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="b04be-109">[in] Le dimensioni del buffer di output, viene utilizzato per la risposta.</span><span class="sxs-lookup"><span data-stu-id="b04be-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="b04be-110">[out] Un Buffer contenente la risposta.</span><span class="sxs-lookup"><span data-stu-id="b04be-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b04be-111">Note</span><span class="sxs-lookup"><span data-stu-id="b04be-111">Remarks</span></span>  
 <span data-ttu-id="b04be-112">Il `Request` metodo semplifica l'aggiunta di operazioni personalizzate non specificate.</span><span class="sxs-lookup"><span data-stu-id="b04be-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="b04be-113">Questo metodo, fornisce l'estendibilità senza richiedere una revisione della definizione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b04be-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="b04be-114">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="b04be-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b04be-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b04be-115">Requirements</span></span>  
 <span data-ttu-id="b04be-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b04be-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b04be-117">**Intestazione:** Clrdata. idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="b04be-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b04be-118">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b04be-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b04be-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b04be-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b04be-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b04be-120">See Also</span></span>  
 [<span data-ttu-id="b04be-121">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="b04be-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
