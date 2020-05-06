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
ms.openlocfilehash: 63c92e3f34527f895552f45d43f332f778470b13
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860431"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="2a0df-102">Metodo ICLRDataTarget3::GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="2a0df-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="2a0df-103">Chiamato dai servizi di accesso ai dati CLR (Common Language Runtime) per ottenere l'ID del thread che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2a0df-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a0df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a0df-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a0df-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2a0df-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="2a0df-106">[out] ID del thread che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2a0df-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a0df-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2a0df-107">Return Value</span></span>  
 <span data-ttu-id="2a0df-108">Il valore restituito è `S_OK` in caso di esito positivo o un codice di errore `HRESULT` in caso di esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2a0df-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="2a0df-109">I codici `HRESULT` possono includere, ma non sono limitati a, quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2a0df-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="2a0df-110">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="2a0df-110">Return code</span></span>|<span data-ttu-id="2a0df-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a0df-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="2a0df-112">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="2a0df-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="2a0df-113">Non è possibile trovare un ID di thread valido per l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2a0df-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a0df-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2a0df-114">Remarks</span></span>  
 <span data-ttu-id="2a0df-115">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="2a0df-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a0df-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2a0df-116">Requirements</span></span>  
 <span data-ttu-id="2a0df-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a0df-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a0df-118">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="2a0df-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2a0df-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a0df-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a0df-120">**Versioni .NET Framework:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2a0df-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a0df-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a0df-121">See also</span></span>

- [<span data-ttu-id="2a0df-122">Interfaccia ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="2a0df-122">ICLRDataTarget3 Interface</span></span>](iclrdatatarget3-interface.md)
- [<span data-ttu-id="2a0df-123">Metodo GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="2a0df-123">GetExceptionContextRecord Method</span></span>](iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="2a0df-124">Metodo GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="2a0df-124">GetExceptionRecord Method</span></span>](iclrdatatarget3-getexceptionrecord-method.md)
