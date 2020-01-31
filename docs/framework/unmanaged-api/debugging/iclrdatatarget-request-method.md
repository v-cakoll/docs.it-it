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
ms.openlocfilehash: 0a7e764d89dd42bcaf81da5cf6a16991b6b8a16e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793698"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="e4d4b-102">Metodo ICLRDataTarget::Request</span><span class="sxs-lookup"><span data-stu-id="e4d4b-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="e4d4b-103">Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per richiedere un'operazione, come definito dall'implementazione di.</span><span class="sxs-lookup"><span data-stu-id="e4d4b-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4d4b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4d4b-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e4d4b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e4d4b-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="e4d4b-106">in Definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e4d4b-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="e4d4b-107">in Dimensioni del buffer di input, che viene utilizzato per la richiesta in ingresso.</span><span class="sxs-lookup"><span data-stu-id="e4d4b-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="e4d4b-108">in Buffer contenente la richiesta.</span><span class="sxs-lookup"><span data-stu-id="e4d4b-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="e4d4b-109">in Dimensione del buffer di output utilizzata per la risposta.</span><span class="sxs-lookup"><span data-stu-id="e4d4b-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="e4d4b-110">out Buffer contenente la risposta.</span><span class="sxs-lookup"><span data-stu-id="e4d4b-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4d4b-111">Note</span><span class="sxs-lookup"><span data-stu-id="e4d4b-111">Remarks</span></span>  
 <span data-ttu-id="e4d4b-112">Il metodo `Request` facilita l'aggiunta di operazioni personalizzate non specificate.</span><span class="sxs-lookup"><span data-stu-id="e4d4b-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="e4d4b-113">Questo metodo fornisce l'estendibilità senza richiedere la revisione della definizione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e4d4b-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="e4d4b-114">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="e4d4b-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4d4b-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e4d4b-115">Requirements</span></span>  
 <span data-ttu-id="e4d4b-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4d4b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4d4b-117">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="e4d4b-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e4d4b-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4d4b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4d4b-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4d4b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4d4b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4d4b-120">See also</span></span>

- [<span data-ttu-id="e4d4b-121">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="e4d4b-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
