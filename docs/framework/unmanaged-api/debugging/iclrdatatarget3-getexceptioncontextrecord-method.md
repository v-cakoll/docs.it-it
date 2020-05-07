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
ms.openlocfilehash: 3e73d0fc48dcfeafb3fe2f23ec07cdc04a561a9e
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860456"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a><span data-ttu-id="3de6e-102">Metodo ICLRDataTarget3::GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="3de6e-102">ICLRDataTarget3::GetExceptionContextRecord Method</span></span>
<span data-ttu-id="3de6e-103">Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per recuperare il record di contesto associato al processo destinazione.</span><span class="sxs-lookup"><span data-stu-id="3de6e-103">Called by the common language runtime (CLR) data access services to retrieve the context record associated with the target process.</span></span> <span data-ttu-id="3de6e-104">Ad esempio, per una destinazione del dump, ciò equivale al record di contesto passato tramite l' `ExceptionParam` argomento alla funzione [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) nella libreria della Guida di debug di Windows (dbghelp).</span><span class="sxs-lookup"><span data-stu-id="3de6e-104">For example, for a dump target, this would be equivalent to the context record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3de6e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3de6e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3de6e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3de6e-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="3de6e-107">[in] La dimensione del buffer di input, in byte.</span><span class="sxs-lookup"><span data-stu-id="3de6e-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="3de6e-108">Questa deve essere sufficientemente grande per poter contenere il record di contesto.</span><span class="sxs-lookup"><span data-stu-id="3de6e-108">This must be large enough to accommodate the context record.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="3de6e-109">[out] Un puntatore a un tipo `ULONG32` che riceve il numero di byte effettivamente scritti nel buffer.</span><span class="sxs-lookup"><span data-stu-id="3de6e-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="3de6e-110">[out] Un puntatore a un buffer di memoria che riceve una copia del record di contesto.</span><span class="sxs-lookup"><span data-stu-id="3de6e-110">[out] A pointer to a memory buffer that receives a copy of the context record.</span></span> <span data-ttu-id="3de6e-111">Il record di eccezione viene restituito come tipo di [contesto](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .</span><span class="sxs-lookup"><span data-stu-id="3de6e-111">The exception record is returned as a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3de6e-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3de6e-112">Return Value</span></span>  
 <span data-ttu-id="3de6e-113">Il valore restituito è `S_OK` in caso di esito positivo o un codice di errore `HRESULT` in caso di esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3de6e-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="3de6e-114">I codici `HRESULT` possono includere, ma non sono limitati a, quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3de6e-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="3de6e-115">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="3de6e-115">Return code</span></span>|<span data-ttu-id="3de6e-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3de6e-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="3de6e-117">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="3de6e-117">Method succeeded.</span></span> <span data-ttu-id="3de6e-118">Il record di contesto è stato copiato nel buffer di output.</span><span class="sxs-lookup"><span data-stu-id="3de6e-118">The context record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="3de6e-119">Nessun record di contesto è associato alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="3de6e-119">No context record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="3de6e-120">La dimensione del buffer di input non è sufficientemente grande per poter contenere il record di contesto.</span><span class="sxs-lookup"><span data-stu-id="3de6e-120">The input buffer size is not large enough to accommodate the context record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3de6e-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3de6e-121">Remarks</span></span>  
 <span data-ttu-id="3de6e-122">[Context](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) è una struttura specifica della piattaforma definita nelle intestazioni fornite dal Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="3de6e-122">[CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) is a platform-specific structure defined in headers provided by the Windows SDK.</span></span>  
  
 <span data-ttu-id="3de6e-123">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="3de6e-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3de6e-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3de6e-124">Requirements</span></span>  
 <span data-ttu-id="3de6e-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3de6e-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3de6e-126">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="3de6e-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3de6e-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3de6e-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3de6e-128">**Versioni .NET Framework:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3de6e-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3de6e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3de6e-129">See also</span></span>

- [<span data-ttu-id="3de6e-130">Interfaccia ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="3de6e-130">ICLRDataTarget3 Interface</span></span>](iclrdatatarget3-interface.md)
- [<span data-ttu-id="3de6e-131">Metodo GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="3de6e-131">GetExceptionRecord Method</span></span>](iclrdatatarget3-getexceptionrecord-method.md)
- [<span data-ttu-id="3de6e-132">Metodo GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="3de6e-132">GetExceptionThreadID Method</span></span>](iclrdatatarget3-getexceptionthreadid-method.md)
