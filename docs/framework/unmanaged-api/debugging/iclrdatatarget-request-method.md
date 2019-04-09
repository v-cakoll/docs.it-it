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
ms.openlocfilehash: e9005dd8fde0d7258bd1dd48b561e4925e87733b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102693"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="59a29-102">Metodo ICLRDataTarget::Request</span><span class="sxs-lookup"><span data-stu-id="59a29-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="59a29-103">Chiamato dai servizi di accesso ai dati di common language runtime (CLR) per richiedere un'operazione, come definito dall'implementazione.</span><span class="sxs-lookup"><span data-stu-id="59a29-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59a29-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59a29-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="59a29-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="59a29-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="59a29-106">[in] Definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="59a29-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="59a29-107">[in] Le dimensioni del buffer di input, che viene usato per la richiesta in ingresso.</span><span class="sxs-lookup"><span data-stu-id="59a29-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="59a29-108">[in] Un buffer contenente la richiesta.</span><span class="sxs-lookup"><span data-stu-id="59a29-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="59a29-109">[in] Le dimensioni del buffer di output, che viene usato per la risposta.</span><span class="sxs-lookup"><span data-stu-id="59a29-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="59a29-110">[out] Un Buffer contenente la risposta.</span><span class="sxs-lookup"><span data-stu-id="59a29-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59a29-111">Note</span><span class="sxs-lookup"><span data-stu-id="59a29-111">Remarks</span></span>  
 <span data-ttu-id="59a29-112">Il `Request` metodo semplifica l'aggiunta di operazioni personalizzate non specificate.</span><span class="sxs-lookup"><span data-stu-id="59a29-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="59a29-113">Vale a dire, questo metodo fornisce estensibilità senza la necessità di revisione della definizione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="59a29-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="59a29-114">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="59a29-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59a29-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="59a29-115">Requirements</span></span>  
 <span data-ttu-id="59a29-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59a29-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59a29-117">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="59a29-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="59a29-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59a29-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="59a29-119">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="59a29-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="59a29-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59a29-120">See also</span></span>

- [<span data-ttu-id="59a29-121">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="59a29-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
