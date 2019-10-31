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
ms.openlocfilehash: a5cda98cac0bc3fc6fb101fd0404b062224cb578
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134087"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="0ddc0-102">Metodo ICorDebug::Initialize</span><span class="sxs-lookup"><span data-stu-id="0ddc0-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="0ddc0-103">Inizializza l'oggetto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="0ddc0-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ddc0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ddc0-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0ddc0-105">Note</span><span class="sxs-lookup"><span data-stu-id="0ddc0-105">Remarks</span></span>  
 <span data-ttu-id="0ddc0-106">Il debugger deve chiamare `Initialize` al momento della creazione per inizializzare i servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="0ddc0-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="0ddc0-107">Questo metodo deve essere chiamato prima di chiamare qualsiasi altro metodo in `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="0ddc0-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ddc0-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ddc0-108">Requirements</span></span>  
 <span data-ttu-id="0ddc0-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ddc0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ddc0-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ddc0-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ddc0-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ddc0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ddc0-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ddc0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ddc0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ddc0-113">See also</span></span>

- [<span data-ttu-id="0ddc0-114">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="0ddc0-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
