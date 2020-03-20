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
ms.openlocfilehash: 336ba38bc80fcb2649a12c78691e52c5e4d70bfe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179119"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="7294e-102">Metodo ICLRDataTarget::Request</span><span class="sxs-lookup"><span data-stu-id="7294e-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="7294e-103">Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per richiedere un'operazione, come definito dall'implementazione.</span><span class="sxs-lookup"><span data-stu-id="7294e-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7294e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7294e-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="7294e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7294e-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="7294e-106">[in] Definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7294e-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="7294e-107">[in] Dimensione del buffer di input, utilizzato per la richiesta in ingresso.</span><span class="sxs-lookup"><span data-stu-id="7294e-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="7294e-108">[in] Buffer contenente la richiesta.</span><span class="sxs-lookup"><span data-stu-id="7294e-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="7294e-109">[in] Dimensione del buffer di output, utilizzato per la risposta.</span><span class="sxs-lookup"><span data-stu-id="7294e-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="7294e-110">[fuori] Oggetto Buffer contenente la risposta.</span><span class="sxs-lookup"><span data-stu-id="7294e-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7294e-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7294e-111">Remarks</span></span>  
 <span data-ttu-id="7294e-112">Il `Request` metodo facilita l'aggiunta di operazioni personalizzate non specificate.</span><span class="sxs-lookup"><span data-stu-id="7294e-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="7294e-113">Ovvero, questo metodo fornisce estensibilità senza richiedere la revisione della definizione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7294e-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="7294e-114">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="7294e-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7294e-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7294e-115">Requirements</span></span>  
 <span data-ttu-id="7294e-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7294e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7294e-117">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="7294e-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7294e-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7294e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7294e-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7294e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7294e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7294e-120">See also</span></span>

- [<span data-ttu-id="7294e-121">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="7294e-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
