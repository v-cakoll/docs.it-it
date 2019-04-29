---
title: Metodo ICLRDataTarget3::GetExceptionThreadID
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionThreadID
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6503efbaa4db89b243a85b69f60b091c6bb49ef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697901"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="78740-102">Metodo ICLRDataTarget3::GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="78740-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="78740-103">Chiamato dai servizi di accesso ai dati CLR (Common Language Runtime) per ottenere l'ID del thread che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="78740-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78740-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78740-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78740-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="78740-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="78740-106">[out] ID del thread che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="78740-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78740-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="78740-107">Return Value</span></span>  
 <span data-ttu-id="78740-108">Il valore restituito è `S_OK` in caso di esito positivo o un codice di errore `HRESULT` in caso di esito negativo.</span><span class="sxs-lookup"><span data-stu-id="78740-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="78740-109">I codici `HRESULT` possono includere, ma non sono limitati a, quanto segue:</span><span class="sxs-lookup"><span data-stu-id="78740-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="78740-110">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="78740-110">Return code</span></span>|<span data-ttu-id="78740-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78740-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="78740-112">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="78740-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="78740-113">Non è possibile trovare un ID di thread valido per l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="78740-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78740-114">Note</span><span class="sxs-lookup"><span data-stu-id="78740-114">Remarks</span></span>  
 <span data-ttu-id="78740-115">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="78740-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78740-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="78740-116">Requirements</span></span>  
 <span data-ttu-id="78740-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78740-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78740-118">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="78740-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="78740-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78740-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78740-120">**Versioni di .NET Framework:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="78740-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78740-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78740-121">See also</span></span>

- [<span data-ttu-id="78740-122">Interfaccia ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="78740-122">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [<span data-ttu-id="78740-123">Metodo GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="78740-123">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="78740-124">Metodo GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="78740-124">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
