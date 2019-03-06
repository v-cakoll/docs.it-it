---
title: Metodo ICorDebugEval2::NewStringWithLength
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewStringWithLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b84a2fad53feda2996515781035c0eaad5828d54
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473435"
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="ab58e-102">Metodo ICorDebugEval2::NewStringWithLength</span><span class="sxs-lookup"><span data-stu-id="ab58e-102">ICorDebugEval2::NewStringWithLength Method</span></span>
<span data-ttu-id="ab58e-103">Crea una stringa di lunghezza specificata, con il contenuto specificato.</span><span class="sxs-lookup"><span data-stu-id="ab58e-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab58e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab58e-104">Syntax</span></span>  
  
```  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab58e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ab58e-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="ab58e-106">[in] Puntatore al valore stringa.</span><span class="sxs-lookup"><span data-stu-id="ab58e-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="ab58e-107">[in] Lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="ab58e-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab58e-108">Note</span><span class="sxs-lookup"><span data-stu-id="ab58e-108">Remarks</span></span>  
 <span data-ttu-id="ab58e-109">Se finale della stringa carattere null deve essere nella stringa gestita, il chiamante del `NewStringWithLength` metodo è necessario assicurarsi che la lunghezza della stringa include il carattere null finale.</span><span class="sxs-lookup"><span data-stu-id="ab58e-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="ab58e-110">La stringa viene sempre creata nel dominio dell'applicazione in cui il thread è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ab58e-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab58e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ab58e-111">Requirements</span></span>  
 <span data-ttu-id="ab58e-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab58e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab58e-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab58e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab58e-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab58e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab58e-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab58e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
