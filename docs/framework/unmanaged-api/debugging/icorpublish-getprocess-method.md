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
ms.openlocfilehash: 46f047dbec7ff008873540806b76ffe7085086b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178426"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="e2a04-102">Metodo ICorPublish::GetProcess</span><span class="sxs-lookup"><span data-stu-id="e2a04-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="e2a04-103">Ottiene un [ICorPublishProcess](icorpublishprocess-interface.md) istanza che rappresenta il processo con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="e2a04-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2a04-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2a04-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2a04-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2a04-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="e2a04-106">[in] Identificatore del processo.</span><span class="sxs-lookup"><span data-stu-id="e2a04-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="e2a04-107">[fuori] Puntatore all'indirizzo `ICorPublishProcess` di un'istanza che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="e2a04-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2a04-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e2a04-108">Remarks</span></span>  
 <span data-ttu-id="e2a04-109">`GetProcess`ha esito negativo se il processo non esiste o non è un processo gestito che può essere sottoposto a debug dall'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="e2a04-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2a04-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2a04-110">Requirements</span></span>  
 <span data-ttu-id="e2a04-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2a04-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2a04-112">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="e2a04-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e2a04-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2a04-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2a04-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2a04-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2a04-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2a04-115">See also</span></span>

- [<span data-ttu-id="e2a04-116">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="e2a04-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
