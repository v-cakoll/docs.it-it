---
title: Metodo ICorDebugVariableHome::GetOffset
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0fdab81d499fe1508493cb0bf05a1787974a9d01
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774532"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="398fe-102">Metodo ICorDebugVariableHome::GetOffset</span><span class="sxs-lookup"><span data-stu-id="398fe-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="398fe-103">Ottiene l'offset del Registro di base per una variabile.</span><span class="sxs-lookup"><span data-stu-id="398fe-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="398fe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="398fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="398fe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="398fe-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="398fe-106">[out] L'offset dalla base registratore di cassa.</span><span class="sxs-lookup"><span data-stu-id="398fe-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="398fe-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="398fe-107">Return Value</span></span>  
 <span data-ttu-id="398fe-108">Il metodo restituisce i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="398fe-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="398fe-109">Value</span><span class="sxs-lookup"><span data-stu-id="398fe-109">Value</span></span>|<span data-ttu-id="398fe-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="398fe-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="398fe-111">La variabile è in una posizione di memoria relativo al registro.</span><span class="sxs-lookup"><span data-stu-id="398fe-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="398fe-112">La variabile non è presente in una posizione di memoria relativo al registro.</span><span class="sxs-lookup"><span data-stu-id="398fe-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="398fe-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="398fe-113">Requirements</span></span>  
 <span data-ttu-id="398fe-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="398fe-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="398fe-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="398fe-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="398fe-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="398fe-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="398fe-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="398fe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="398fe-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="398fe-118">See also</span></span>

- [<span data-ttu-id="398fe-119">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="398fe-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
