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
ms.openlocfilehash: 9ee6f43c94b8ff2e765d2a0dde0697c4c895a94f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212373"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="78c37-102">Metodo ICorDebugManagedCallback::UpdateModuleSymbols</span><span class="sxs-lookup"><span data-stu-id="78c37-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="78c37-103">Notifica al debugger che i simboli per un modulo Common Language Runtime sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="78c37-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78c37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78c37-104">Syntax</span></span>  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78c37-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="78c37-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="78c37-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il modulo in cui sono stati modificati i simboli.</span><span class="sxs-lookup"><span data-stu-id="78c37-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="78c37-107">in Puntatore a un oggetto ICorDebugModule che rappresenta il modulo in cui sono stati modificati i simboli.</span><span class="sxs-lookup"><span data-stu-id="78c37-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="78c37-108">in Puntatore a un oggetto COM Win32 `IStream` che contiene i simboli modificati.</span><span class="sxs-lookup"><span data-stu-id="78c37-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78c37-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="78c37-109">Remarks</span></span>  
 <span data-ttu-id="78c37-110">Questo metodo offre la possibilità di aggiornare la visualizzazione del debugger dei simboli di un modulo chiamando [ISymUnmanagedReader:: UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) o [ISymUnmanagedReader:: ReplaceSymbolStore](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span><span class="sxs-lookup"><span data-stu-id="78c37-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="78c37-111">Questo callback può essere eseguito più volte per lo stesso modulo.</span><span class="sxs-lookup"><span data-stu-id="78c37-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="78c37-112">Un debugger deve tentare di associare i punti di interruzione a livello di origine non associati.</span><span class="sxs-lookup"><span data-stu-id="78c37-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78c37-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="78c37-113">Requirements</span></span>  
 <span data-ttu-id="78c37-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78c37-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78c37-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78c37-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78c37-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78c37-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78c37-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78c37-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78c37-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78c37-118">See also</span></span>

- [<span data-ttu-id="78c37-119">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="78c37-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
