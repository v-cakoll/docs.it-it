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
ms.openlocfilehash: 2cd2238ac67713564922be440ce64a2ebc4bbf44
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396339"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="627a3-102">Metodo ICorPublish::GetProcess</span><span class="sxs-lookup"><span data-stu-id="627a3-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="627a3-103">Ottiene un'istanza di [ICorPublishProcess](icorpublishprocess-interface.md) che rappresenta il processo con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="627a3-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="627a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="627a3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="627a3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="627a3-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="627a3-106">in Identificatore del processo.</span><span class="sxs-lookup"><span data-stu-id="627a3-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="627a3-107">out Puntatore all'indirizzo di un' `ICorPublishProcess` istanza che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="627a3-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="627a3-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="627a3-108">Remarks</span></span>  
 <span data-ttu-id="627a3-109">`GetProcess`ha esito negativo se il processo non esiste o non è un processo gestito che può essere sottoposto a debug dall'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="627a3-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="627a3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="627a3-110">Requirements</span></span>  
 <span data-ttu-id="627a3-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="627a3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="627a3-112">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="627a3-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="627a3-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="627a3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="627a3-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="627a3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="627a3-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="627a3-115">See also</span></span>

- [<span data-ttu-id="627a3-116">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="627a3-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
