---
title: Metodo ICorDebugManagedCallback::Break
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.Break
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ce51ed25ecd5570ce3c5d9acc1ec3750b289f095
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="6801b-102">Metodo ICorDebugManagedCallback::Break</span><span class="sxs-lookup"><span data-stu-id="6801b-102">ICorDebugManagedCallback::Break Method</span></span>
<span data-ttu-id="6801b-103">Notifica al debugger quando un <xref:System.Reflection.Emit.OpCodes.Break> un'istruzione nel flusso del codice.</span><span class="sxs-lookup"><span data-stu-id="6801b-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6801b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6801b-104">Syntax</span></span>  
  
```  
HRESULT Break (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6801b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6801b-105">Parameters</span></span>  
 `pAppDOmain`  
 <span data-ttu-id="6801b-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene l'istruzione di interruzione.</span><span class="sxs-lookup"><span data-stu-id="6801b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>  
  
 `thread`  
 <span data-ttu-id="6801b-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread che contiene l'istruzione di interruzione.</span><span class="sxs-lookup"><span data-stu-id="6801b-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6801b-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6801b-108">Requirements</span></span>  
 <span data-ttu-id="6801b-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6801b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6801b-110">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="6801b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6801b-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6801b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6801b-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6801b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6801b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6801b-113">See Also</span></span>  
 [<span data-ttu-id="6801b-114">ICorDebugManagedCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6801b-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
