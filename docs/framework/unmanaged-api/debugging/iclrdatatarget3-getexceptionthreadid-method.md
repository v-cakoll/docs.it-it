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
ms.openlocfilehash: 961e74551ae7fc170e443c632ca11598f1494a39
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785212"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="864bb-102">Metodo ICLRDataTarget3::GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="864bb-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="864bb-103">Chiamato dai servizi di accesso ai dati CLR (Common Language Runtime) per ottenere l'ID del thread che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="864bb-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="864bb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="864bb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="864bb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="864bb-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="864bb-106">[out] ID del thread che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="864bb-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="864bb-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="864bb-107">Return Value</span></span>  
 <span data-ttu-id="864bb-108">Il valore restituito è `S_OK` in caso di esito positivo o un codice di errore `HRESULT` in caso di esito negativo.</span><span class="sxs-lookup"><span data-stu-id="864bb-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="864bb-109">I codici `HRESULT` possono includere, ma non sono limitati a, quanto segue:</span><span class="sxs-lookup"><span data-stu-id="864bb-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="864bb-110">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="864bb-110">Return code</span></span>|<span data-ttu-id="864bb-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="864bb-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="864bb-112">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="864bb-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="864bb-113">Non è possibile trovare un ID di thread valido per l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="864bb-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="864bb-114">Note</span><span class="sxs-lookup"><span data-stu-id="864bb-114">Remarks</span></span>  
 <span data-ttu-id="864bb-115">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="864bb-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="864bb-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="864bb-116">Requirements</span></span>  
 <span data-ttu-id="864bb-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="864bb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="864bb-118">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="864bb-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="864bb-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="864bb-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="864bb-120">**Versioni .NET Framework:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="864bb-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="864bb-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="864bb-121">See also</span></span>

- [<span data-ttu-id="864bb-122">Interfaccia ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="864bb-122">ICLRDataTarget3 Interface</span></span>](iclrdatatarget3-interface.md)
- [<span data-ttu-id="864bb-123">Metodo GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="864bb-123">GetExceptionContextRecord Method</span></span>](iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="864bb-124">Metodo GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="864bb-124">GetExceptionRecord Method</span></span>](iclrdatatarget3-getexceptionrecord-method.md)
