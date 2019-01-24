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
ms.openlocfilehash: f7b4cf6c50d624f82a75f19b8e3f42c73910c4e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709299"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="033f1-102">Metodo ICorDebug::Initialize</span><span class="sxs-lookup"><span data-stu-id="033f1-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="033f1-103">Inizializza il `ICorDebug` oggetto.</span><span class="sxs-lookup"><span data-stu-id="033f1-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="033f1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="033f1-104">Syntax</span></span>  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="033f1-105">Note</span><span class="sxs-lookup"><span data-stu-id="033f1-105">Remarks</span></span>  
 <span data-ttu-id="033f1-106">Il debugger deve chiamare `Initialize` al momento della creazione di servizi tempo necessario per inizializzare il debug.</span><span class="sxs-lookup"><span data-stu-id="033f1-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="033f1-107">Questo metodo deve essere chiamato prima di qualsiasi altro metodo nel `ICorDebug` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="033f1-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="033f1-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="033f1-108">Requirements</span></span>  
 <span data-ttu-id="033f1-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="033f1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="033f1-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="033f1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="033f1-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="033f1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="033f1-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="033f1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="033f1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="033f1-113">See also</span></span>
- [<span data-ttu-id="033f1-114">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="033f1-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
