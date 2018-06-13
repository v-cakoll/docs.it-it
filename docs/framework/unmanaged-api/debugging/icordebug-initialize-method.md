---
title: Metodo ICorDebug::Initialize
ms.date: 03/30/2017
api_name:
- ICorDebug.Initialize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa79382d597d303d492e3a441c15a422697be279
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405967"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="b4eb3-102">Metodo ICorDebug::Initialize</span><span class="sxs-lookup"><span data-stu-id="b4eb3-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="b4eb3-103">Inizializza il `ICorDebug` oggetto.</span><span class="sxs-lookup"><span data-stu-id="b4eb3-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4eb3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4eb3-104">Syntax</span></span>  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="b4eb3-105">Note</span><span class="sxs-lookup"><span data-stu-id="b4eb3-105">Remarks</span></span>  
 <span data-ttu-id="b4eb3-106">Il debugger deve chiamare `Initialize` al momento della creazione di servizi ora per inizializzare il debug.</span><span class="sxs-lookup"><span data-stu-id="b4eb3-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="b4eb3-107">Questo metodo deve essere chiamato prima di qualsiasi altro metodo per `ICorDebug` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="b4eb3-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4eb3-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b4eb3-108">Requirements</span></span>  
 <span data-ttu-id="b4eb3-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4eb3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4eb3-110">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="b4eb3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4eb3-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b4eb3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4eb3-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4eb3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4eb3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4eb3-113">See Also</span></span>  
 [<span data-ttu-id="b4eb3-114">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="b4eb3-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
