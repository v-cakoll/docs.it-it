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
ms.openlocfilehash: a2b76cb59a95082e0cf9c0884b8277cca3c8fe8d
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976070"
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="07d97-102">Metodo ICorDebugEval2::NewStringWithLength</span><span class="sxs-lookup"><span data-stu-id="07d97-102">ICorDebugEval2::NewStringWithLength Method</span></span>
<span data-ttu-id="07d97-103">Crea una stringa della lunghezza specificata, con il contenuto specificato.</span><span class="sxs-lookup"><span data-stu-id="07d97-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07d97-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07d97-104">Syntax</span></span>  
  
```cpp  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07d97-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="07d97-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="07d97-106">in Puntatore al valore stringa.</span><span class="sxs-lookup"><span data-stu-id="07d97-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="07d97-107">in Lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="07d97-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07d97-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="07d97-108">Remarks</span></span>  
 <span data-ttu-id="07d97-109">Se si prevede che il carattere null finale della stringa si trovi nella stringa gestita, il chiamante del `NewStringWithLength` metodo deve garantire che la lunghezza della stringa includa il carattere null finale.</span><span class="sxs-lookup"><span data-stu-id="07d97-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="07d97-110">La stringa viene sempre creata nel dominio applicazione in cui è attualmente in esecuzione il thread.</span><span class="sxs-lookup"><span data-stu-id="07d97-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07d97-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="07d97-111">Requirements</span></span>  
 <span data-ttu-id="07d97-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07d97-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07d97-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07d97-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07d97-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07d97-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07d97-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07d97-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
