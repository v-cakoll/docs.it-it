---
title: Metodo ICorDebugEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
ms.openlocfilehash: 64d9db09b3e604247ab6a26cdca9eca22adbaace
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976304"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="4cc8a-102">Metodo ICorDebugEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="4cc8a-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="4cc8a-103">Sposta il cursore verso l'interno dell'enumerazione in base al numero di elementi specificato.</span><span class="sxs-lookup"><span data-stu-id="4cc8a-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cc8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4cc8a-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cc8a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4cc8a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="4cc8a-106">in Numero di elementi in base ai quali spostare il cursore avanti.</span><span class="sxs-lookup"><span data-stu-id="4cc8a-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cc8a-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4cc8a-107">Requirements</span></span>  
 <span data-ttu-id="4cc8a-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cc8a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cc8a-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4cc8a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cc8a-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cc8a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cc8a-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cc8a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc8a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cc8a-112">See also</span></span>

- [<span data-ttu-id="4cc8a-113">Interfaccia ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="4cc8a-113">ICorDebugEnum Interface</span></span>](icordebugenum-interface1.md)
