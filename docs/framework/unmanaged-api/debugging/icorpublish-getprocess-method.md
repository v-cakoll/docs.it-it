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
ms.openlocfilehash: 0368349e6c6a566cb569738bf3bda40eb9f5de96
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790742"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="7926e-102">Metodo ICorPublish::GetProcess</span><span class="sxs-lookup"><span data-stu-id="7926e-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="7926e-103">Ottiene un'istanza di [ICorPublishProcess](icorpublishprocess-interface.md) che rappresenta il processo con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="7926e-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7926e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7926e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7926e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7926e-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="7926e-106">in Identificatore del processo.</span><span class="sxs-lookup"><span data-stu-id="7926e-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="7926e-107">out Puntatore all'indirizzo di un'istanza `ICorPublishProcess` che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="7926e-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7926e-108">Note</span><span class="sxs-lookup"><span data-stu-id="7926e-108">Remarks</span></span>  
 <span data-ttu-id="7926e-109">`GetProcess` ha esito negativo se il processo non esiste o non è un processo gestito che può essere sottoposto a debug dall'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="7926e-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7926e-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="7926e-110">Requirements</span></span>  
 <span data-ttu-id="7926e-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7926e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7926e-112">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="7926e-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="7926e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7926e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7926e-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7926e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7926e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7926e-115">See also</span></span>

- [<span data-ttu-id="7926e-116">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="7926e-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
