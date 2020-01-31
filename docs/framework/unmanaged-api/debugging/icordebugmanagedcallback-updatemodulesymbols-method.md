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
ms.openlocfilehash: 2b64122489481c6b0fde605015720d0a56ba8fe2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788320"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="d43de-102">Metodo ICorDebugManagedCallback::UpdateModuleSymbols</span><span class="sxs-lookup"><span data-stu-id="d43de-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="d43de-103">Notifica al debugger che i simboli per un modulo Common Language Runtime sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="d43de-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d43de-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d43de-104">Syntax</span></span>  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d43de-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d43de-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d43de-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il modulo in cui sono stati modificati i simboli.</span><span class="sxs-lookup"><span data-stu-id="d43de-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="d43de-107">in Puntatore a un oggetto ICorDebugModule che rappresenta il modulo in cui sono stati modificati i simboli.</span><span class="sxs-lookup"><span data-stu-id="d43de-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="d43de-108">in Puntatore a un oggetto `IStream` COM Win32 che contiene i simboli modificati.</span><span class="sxs-lookup"><span data-stu-id="d43de-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d43de-109">Note</span><span class="sxs-lookup"><span data-stu-id="d43de-109">Remarks</span></span>  
 <span data-ttu-id="d43de-110">Questo metodo offre la possibilità di aggiornare la visualizzazione del debugger dei simboli di un modulo chiamando [ISymUnmanagedReader:: UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) o [ISymUnmanagedReader:: ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span><span class="sxs-lookup"><span data-stu-id="d43de-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="d43de-111">Questo callback può essere eseguito più volte per lo stesso modulo.</span><span class="sxs-lookup"><span data-stu-id="d43de-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="d43de-112">Un debugger deve tentare di associare i punti di interruzione a livello di origine non associati.</span><span class="sxs-lookup"><span data-stu-id="d43de-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d43de-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="d43de-113">Requirements</span></span>  
 <span data-ttu-id="d43de-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d43de-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d43de-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d43de-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d43de-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d43de-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d43de-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d43de-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d43de-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d43de-118">See also</span></span>

- [<span data-ttu-id="d43de-119">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="d43de-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
