---
title: Metodo ICorPublish::GetProcess
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 414bc1bbd3578d0707e35fa70fe196b504af9942
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418496"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="fa3ce-102">Metodo ICorPublish::GetProcess</span><span class="sxs-lookup"><span data-stu-id="fa3ce-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="fa3ce-103">Ottiene un [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) istanza che rappresenta il processo con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa3ce-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa3ce-104">Syntax</span></span>  
  
```  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa3ce-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fa3ce-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="fa3ce-106">[in] Identificatore del processo.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="fa3ce-107">[out] Un puntatore all'indirizzo di un `ICorPublishProcess` istanza che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa3ce-108">Note</span><span class="sxs-lookup"><span data-stu-id="fa3ce-108">Remarks</span></span>  
 <span data-ttu-id="fa3ce-109">`GetProcess` si verifica un errore se il processo non esiste o non è un processo gestito che può essere eseguito dall'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa3ce-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fa3ce-110">Requirements</span></span>  
 <span data-ttu-id="fa3ce-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa3ce-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa3ce-112">**Intestazione:** Corpub. idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="fa3ce-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="fa3ce-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="fa3ce-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa3ce-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa3ce-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa3ce-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa3ce-115">See Also</span></span>  
 [<span data-ttu-id="fa3ce-116">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="fa3ce-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
