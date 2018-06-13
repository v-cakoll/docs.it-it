---
title: Metodo ICorDebugMutableDataTarget::ContinueStatusChanged
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb07c519743c41a7a31994e42d2fdc5220e5e2ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418211"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a><span data-ttu-id="74261-102">Metodo ICorDebugMutableDataTarget::ContinueStatusChanged</span><span class="sxs-lookup"><span data-stu-id="74261-102">ICorDebugMutableDataTarget::ContinueStatusChanged Method</span></span>
<span data-ttu-id="74261-103">Modifica lo stato di continuazione per l'evento di debug in sospeso sul thread specificato.</span><span class="sxs-lookup"><span data-stu-id="74261-103">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74261-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74261-104">Syntax</span></span>  
  
```  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74261-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="74261-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="74261-106">Identificatore del thread definito dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="74261-106">The operating system-defined thread identifier.</span></span>  
  
 `continueStatus`  
 <span data-ttu-id="74261-107">Oggetto[COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)valore che rappresenta il nuovo stato di continuazione richiesto.</span><span class="sxs-lookup"><span data-stu-id="74261-107">A[COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)value that represents the new requested continuation status.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74261-108">Note</span><span class="sxs-lookup"><span data-stu-id="74261-108">Remarks</span></span>  
 <span data-ttu-id="74261-109">Il debugger chiama il metodo `ContinueStatusChanged` quando chiama un metodo ICorDebug che richiede di gestire l'evento di debug corrente in modo potenzialmente diverso da quello in cui verrebbe gestito di solito.</span><span class="sxs-lookup"><span data-stu-id="74261-109">The debugger calls the `ContinueStatusChanged` method when it calls an ICorDebug method that requires the current debug event to be handled in a way that is potentially different from the way in which it normally would be handled.</span></span> <span data-ttu-id="74261-110">Ad esempio, se si verifica un'eccezione in sospeso e il debugger richiede un'operazione che annullerebbe l'accezione (ad esempio [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) o `FuncEval`), questa API viene usata per richiedere che l'eccezione venga annullata.</span><span class="sxs-lookup"><span data-stu-id="74261-110">For example, if there is an outstanding exception, and the debugger requests an operation that would cancel the exception (such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or `FuncEval`), this API is used to request that the exception be cancelled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74261-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74261-111">Requirements</span></span>  
 <span data-ttu-id="74261-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74261-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74261-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="74261-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74261-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="74261-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74261-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74261-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74261-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74261-116">See Also</span></span>  
 [<span data-ttu-id="74261-117">Interfaccia ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="74261-117">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="74261-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="74261-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
