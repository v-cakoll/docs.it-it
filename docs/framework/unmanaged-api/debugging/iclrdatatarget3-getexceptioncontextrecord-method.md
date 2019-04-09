---
title: Metodo ICLRDataTarget3::GetExceptionContextRecord
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetContextRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b43ab8cdeff3866bb51e8634f367cf86ee483d4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089231"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a><span data-ttu-id="235e6-102">Metodo ICLRDataTarget3::GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="235e6-102">ICLRDataTarget3::GetExceptionContextRecord Method</span></span>
<span data-ttu-id="235e6-103">Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per recuperare il record di contesto associato al processo destinazione.</span><span class="sxs-lookup"><span data-stu-id="235e6-103">Called by the common language runtime (CLR) data access services to retrieve the context record associated with the target process.</span></span> <span data-ttu-id="235e6-104">Ad esempio, per una destinazione del dump, sarebbe equivalente al record di contesto passato tramite la `ExceptionParam` argomento per il [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) (funzione) in Windows eseguire il Debug della Guida Library (DbgHelp).</span><span class="sxs-lookup"><span data-stu-id="235e6-104">For example, for a dump target, this would be equivalent to the context record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="235e6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="235e6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="235e6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="235e6-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="235e6-107">[in] La dimensione del buffer di input, in byte.</span><span class="sxs-lookup"><span data-stu-id="235e6-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="235e6-108">Questa deve essere sufficientemente grande per poter contenere il record di contesto.</span><span class="sxs-lookup"><span data-stu-id="235e6-108">This must be large enough to accommodate the context record.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="235e6-109">[out] Un puntatore a un tipo `ULONG32` che riceve il numero di byte effettivamente scritti nel buffer.</span><span class="sxs-lookup"><span data-stu-id="235e6-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="235e6-110">[out] Un puntatore a un buffer di memoria che riceve una copia del record di contesto.</span><span class="sxs-lookup"><span data-stu-id="235e6-110">[out] A pointer to a memory buffer that receives a copy of the context record.</span></span> <span data-ttu-id="235e6-111">Il record di eccezione viene restituito come un [contesto](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) tipo.</span><span class="sxs-lookup"><span data-stu-id="235e6-111">The exception record is returned as a [CONTEXT](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="235e6-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="235e6-112">Return Value</span></span>  
 <span data-ttu-id="235e6-113">Il valore restituito è `S_OK` in caso di esito positivo o un codice di errore `HRESULT` in caso di esito negativo.</span><span class="sxs-lookup"><span data-stu-id="235e6-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="235e6-114">I codici `HRESULT` possono includere, ma non sono limitati a, quanto segue:</span><span class="sxs-lookup"><span data-stu-id="235e6-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="235e6-115">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="235e6-115">Return code</span></span>|<span data-ttu-id="235e6-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="235e6-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="235e6-117">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="235e6-117">Method succeeded.</span></span> <span data-ttu-id="235e6-118">Il record di contesto è stato copiato nel buffer di output.</span><span class="sxs-lookup"><span data-stu-id="235e6-118">The context record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="235e6-119">Nessun record di contesto è associato alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="235e6-119">No context record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="235e6-120">La dimensione del buffer di input non è sufficientemente grande per poter contenere il record di contesto.</span><span class="sxs-lookup"><span data-stu-id="235e6-120">The input buffer size is not large enough to accommodate the context record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="235e6-121">Note</span><span class="sxs-lookup"><span data-stu-id="235e6-121">Remarks</span></span>  
 <span data-ttu-id="235e6-122">[CONTESTO](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) è una struttura specifica della piattaforma definita nelle intestazioni fornite da Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="235e6-122">[CONTEXT](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) is a platform-specific structure defined in headers provided by the Windows SDK.</span></span>  
  
 <span data-ttu-id="235e6-123">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="235e6-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="235e6-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="235e6-124">Requirements</span></span>  
 <span data-ttu-id="235e6-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="235e6-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="235e6-126">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="235e6-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="235e6-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="235e6-127">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="235e6-128">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="235e6-128">.NET Framework Versions:</span></span>** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="235e6-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="235e6-129">See also</span></span>

- [<span data-ttu-id="235e6-130">Interfaccia ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="235e6-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [<span data-ttu-id="235e6-131">Metodo GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="235e6-131">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
- [<span data-ttu-id="235e6-132">Metodo GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="235e6-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
