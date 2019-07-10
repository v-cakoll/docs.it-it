---
title: Metodo ICorDebugManagedCallback::UpdateModuleSymbols
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UpdateModuleSymbols
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a15e3ab0d50763ad53b1caa921035239868fec1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761238"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="9b825-102">Metodo ICorDebugManagedCallback::UpdateModuleSymbols</span><span class="sxs-lookup"><span data-stu-id="9b825-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="9b825-103">Notifica al debugger che sono stati modificati i simboli per un modulo di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="9b825-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b825-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b825-104">Syntax</span></span>  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b825-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9b825-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9b825-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio dell'applicazione che contiene il modulo in cui sono stati modificati i simboli.</span><span class="sxs-lookup"><span data-stu-id="9b825-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="9b825-107">[in] Un puntatore a un oggetto ICorDebugModule che rappresenta il modulo in cui sono stati modificati i simboli.</span><span class="sxs-lookup"><span data-stu-id="9b825-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="9b825-108">[in] Un puntatore a COM Win32 `IStream` oggetto che contiene i simboli modificati.</span><span class="sxs-lookup"><span data-stu-id="9b825-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b825-109">Note</span><span class="sxs-lookup"><span data-stu-id="9b825-109">Remarks</span></span>  
 <span data-ttu-id="9b825-110">Questo metodo offre la possibilità di aggiornare la visualizzazione del debugger di simboli di un modulo chiamando [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) oppure [ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span><span class="sxs-lookup"><span data-stu-id="9b825-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="9b825-111">Questo callback può ricorrere più volte per lo stesso modulo.</span><span class="sxs-lookup"><span data-stu-id="9b825-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="9b825-112">Un debugger deve provare a eseguire l'associazione dei punti di interruzione a livello di origine non associati.</span><span class="sxs-lookup"><span data-stu-id="9b825-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b825-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9b825-113">Requirements</span></span>  
 <span data-ttu-id="9b825-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b825-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b825-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b825-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b825-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b825-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b825-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b825-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b825-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b825-118">See also</span></span>

- [<span data-ttu-id="9b825-119">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="9b825-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
