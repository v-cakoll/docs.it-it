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
ms.openlocfilehash: 2a8200f942405395429db182b7501a07fc1f930a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212321"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="fdab1-102">Metodo ICorDebugModule3::CreateReaderForInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="fdab1-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="fdab1-103">Crea un lettore di simboli di debug per un modulo dinamico.</span><span class="sxs-lookup"><span data-stu-id="fdab1-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdab1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fdab1-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdab1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fdab1-105">Parameters</span></span>  
 <span data-ttu-id="fdab1-106">riid</span><span class="sxs-lookup"><span data-stu-id="fdab1-106">riid</span></span>  
 <span data-ttu-id="fdab1-107">in IID dell'interfaccia COM da restituire.</span><span class="sxs-lookup"><span data-stu-id="fdab1-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="fdab1-108">Si tratta in genere di un' [interfaccia ISymUnmanagedReader](../diagnostics/isymunmanagedreader-interface.md).</span><span class="sxs-lookup"><span data-stu-id="fdab1-108">Typically, this is an [ISymUnmanagedReader Interface](../diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="fdab1-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="fdab1-109">ppObj</span></span>  
 <span data-ttu-id="fdab1-110">out Puntatore a un puntatore all'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="fdab1-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fdab1-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fdab1-111">Return Value</span></span>  
 <span data-ttu-id="fdab1-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="fdab1-112">S_OK</span></span>  
 <span data-ttu-id="fdab1-113">Creazione del Reader completata.</span><span class="sxs-lookup"><span data-stu-id="fdab1-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="fdab1-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="fdab1-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="fdab1-115">Il modulo non è un modulo in memoria o dinamico.</span><span class="sxs-lookup"><span data-stu-id="fdab1-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="fdab1-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fdab1-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="fdab1-117">I simboli non sono stati forniti dall'applicazione o non sono ancora disponibili.</span><span class="sxs-lookup"><span data-stu-id="fdab1-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="fdab1-118">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="fdab1-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="fdab1-119">Impossibile creare il lettore.</span><span class="sxs-lookup"><span data-stu-id="fdab1-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdab1-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fdab1-120">Remarks</span></span>  
 <span data-ttu-id="fdab1-121">Questo metodo può essere usato anche per creare un oggetto lettore di simboli per i moduli in memoria (non dinamici), ma solo dopo che i simboli sono disponibili per la prima volta (indicati dal callback del [Metodo UpdateModuleSymbols](icordebugmanagedcallback-updatemodulesymbols-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="fdab1-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="fdab1-122">Questo metodo restituisce una nuova istanza di Reader ogni volta che viene chiamata (ad esempio [CComPtrBase:: CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span><span class="sxs-lookup"><span data-stu-id="fdab1-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span></span> <span data-ttu-id="fdab1-123">Pertanto, il debugger deve memorizzare nella cache il risultato e richiedere una nuova istanza solo quando è possibile che i dati sottostanti siano stati modificati, ovvero quando viene ricevuto un callback del [metodo loadClass](icordebugmanagedcallback-loadclass-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fdab1-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="fdab1-124">I moduli dinamici non hanno alcun simbolo disponibile fino a quando non è stato caricato il primo tipo (come indicato dal callback del [metodo loadClass](icordebugmanagedcallback-loadclass-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="fdab1-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdab1-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fdab1-125">Requirements</span></span>  
 <span data-ttu-id="fdab1-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdab1-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdab1-127">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fdab1-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdab1-128">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdab1-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdab1-129">**Versioni .NET Framework:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="fdab1-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdab1-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdab1-130">See also</span></span>

- [<span data-ttu-id="fdab1-131">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="fdab1-131">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="fdab1-132">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="fdab1-132">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="fdab1-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fdab1-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
