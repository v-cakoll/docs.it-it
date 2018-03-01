---
title: Metodo ICorDebugManagedCallback::UpdateModuleSymbols
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ad5a84268f3810a1fb73a21a6bd8106e82ccbd78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="6b85b-102">Metodo ICorDebugManagedCallback::UpdateModuleSymbols</span><span class="sxs-lookup"><span data-stu-id="6b85b-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="6b85b-103">Notifica al debugger che sono cambiati i simboli per un modulo di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="6b85b-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b85b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b85b-104">Syntax</span></span>  
  
```  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b85b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6b85b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="6b85b-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il modulo in cui sono stati modificati i simboli.</span><span class="sxs-lookup"><span data-stu-id="6b85b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="6b85b-107">[in] Un puntatore a un oggetto ICorDebugModule che rappresenta il modulo in cui sono stati modificati i simboli.</span><span class="sxs-lookup"><span data-stu-id="6b85b-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="6b85b-108">[in] Un puntatore a un COM Win32 `IStream` oggetto che contiene i simboli modificati.</span><span class="sxs-lookup"><span data-stu-id="6b85b-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b85b-109">Note</span><span class="sxs-lookup"><span data-stu-id="6b85b-109">Remarks</span></span>  
 <span data-ttu-id="6b85b-110">Questo metodo offre l'opportunità di aggiornare la visualizzazione del debugger di simboli di un modulo chiamando [ISymUnmanagedReader:: UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) o [ISymUnmanagedReader:: ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span><span class="sxs-lookup"><span data-stu-id="6b85b-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="6b85b-111">Questo callback può ricorrere più volte per il modulo stesso.</span><span class="sxs-lookup"><span data-stu-id="6b85b-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="6b85b-112">Un debugger deve tentare di associare i punti di interruzione a livello di origine non associati.</span><span class="sxs-lookup"><span data-stu-id="6b85b-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b85b-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b85b-113">Requirements</span></span>  
 <span data-ttu-id="6b85b-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b85b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b85b-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="6b85b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b85b-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b85b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b85b-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b85b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b85b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b85b-118">See Also</span></span>  
 [<span data-ttu-id="6b85b-119">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="6b85b-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
