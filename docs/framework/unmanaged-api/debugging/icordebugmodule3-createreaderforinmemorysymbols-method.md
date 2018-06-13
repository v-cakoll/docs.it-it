---
title: Metodo ICorDebugModule3::CreateReaderForInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorDebugModule3.CreateReaderForInMemorySymbols
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76f7b53f800bc8c5c23f49a0781287a38bf8c959
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421516"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="d34e0-102">Metodo ICorDebugModule3::CreateReaderForInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="d34e0-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="d34e0-103">Crea un lettore di simboli di debug per un modulo dinamico.</span><span class="sxs-lookup"><span data-stu-id="d34e0-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d34e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d34e0-104">Syntax</span></span>  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d34e0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d34e0-105">Parameters</span></span>  
 <span data-ttu-id="d34e0-106">riid</span><span class="sxs-lookup"><span data-stu-id="d34e0-106">riid</span></span>  
 <span data-ttu-id="d34e0-107">[in] IID dell'interfaccia COM da restituire.</span><span class="sxs-lookup"><span data-stu-id="d34e0-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="d34e0-108">In genere, si tratta di un [interfaccia ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d34e0-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="d34e0-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="d34e0-109">ppObj</span></span>  
 <span data-ttu-id="d34e0-110">[out] Puntatore a un puntatore all'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="d34e0-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d34e0-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d34e0-111">Return Value</span></span>  
 <span data-ttu-id="d34e0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d34e0-112">S_OK</span></span>  
 <span data-ttu-id="d34e0-113">Ha creato il lettore.</span><span class="sxs-lookup"><span data-stu-id="d34e0-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="d34e0-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="d34e0-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="d34e0-115">Il modulo non è un modulo in memoria o dinamico.</span><span class="sxs-lookup"><span data-stu-id="d34e0-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="d34e0-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d34e0-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="d34e0-117">Simboli non sono stati forniti dall'applicazione o non sono ancora disponibili.</span><span class="sxs-lookup"><span data-stu-id="d34e0-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="d34e0-118">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="d34e0-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="d34e0-119">Impossibile creare il lettore.</span><span class="sxs-lookup"><span data-stu-id="d34e0-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d34e0-120">Note</span><span class="sxs-lookup"><span data-stu-id="d34e0-120">Remarks</span></span>  
 <span data-ttu-id="d34e0-121">Questo metodo può anche essere utilizzato per creare un oggetto del lettore di simboli per i moduli in memoria (non dinamica), ma solo dopo che saranno disponibili i simboli (indicato dal [metodo UpdateModuleSymbols](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span><span class="sxs-lookup"><span data-stu-id="d34e0-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="d34e0-122">Questo metodo restituisce una nuova istanza di lettura ogni volta che viene chiamato (ad esempio [CComPtrBase:: CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)).</span><span class="sxs-lookup"><span data-stu-id="d34e0-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)).</span></span> <span data-ttu-id="d34e0-123">Pertanto, il debugger deve memorizzare nella cache il risultato e richiedere una nuova istanza solo quando i dati sottostanti possono essere modificata (ovvero, quando un [LoadClass (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback viene ricevuto).</span><span class="sxs-lookup"><span data-stu-id="d34e0-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="d34e0-124">Moduli dinamici non dispone i simboli disponibili fino a quando non è stato caricato il primo tipo (come indicato dal [metodo LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span><span class="sxs-lookup"><span data-stu-id="d34e0-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d34e0-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d34e0-125">Requirements</span></span>  
 <span data-ttu-id="d34e0-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d34e0-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d34e0-127">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="d34e0-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d34e0-128">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d34e0-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d34e0-129">**Versioni di .NET framework:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="d34e0-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d34e0-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d34e0-130">See Also</span></span>  
 [<span data-ttu-id="d34e0-131">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="d34e0-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="d34e0-132">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="d34e0-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="d34e0-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d34e0-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
