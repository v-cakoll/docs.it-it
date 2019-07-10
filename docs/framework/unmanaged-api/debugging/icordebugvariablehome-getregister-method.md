---
title: Metodo ICorDebugVariableHome::GetRegister
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4b3b80546095b79dc5b551a9c5e92ec15c0dddb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771794"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="bb4f5-102">Metodo ICorDebugVariableHome::GetRegister</span><span class="sxs-lookup"><span data-stu-id="bb4f5-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="bb4f5-103">Ottiene il registro contenente una variabile con un tipo di posizione di `VLT_REGISTER`e la registrazione di base per una variabile con un tipo di posizione di `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="bb4f5-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb4f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb4f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb4f5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bb4f5-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="bb4f5-106">[out] Un valore di enumerazione CorDebugRegister che indica la registrazione per una variabile con un tipo di posizione di `VLT_REGISTER`e la registrazione di base per una variabile con un tipo di posizione di `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="bb4f5-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb4f5-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bb4f5-107">Return Value</span></span>  
 <span data-ttu-id="bb4f5-108">Il metodo restituisce i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb4f5-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="bb4f5-109">Value</span><span class="sxs-lookup"><span data-stu-id="bb4f5-109">Value</span></span>|<span data-ttu-id="bb4f5-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb4f5-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="bb4f5-111">La variabile è il registro indicato dal `pRegister` argomento.</span><span class="sxs-lookup"><span data-stu-id="bb4f5-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="bb4f5-112">La variabile non è presente in un registro o un percorso relativo al registro.</span><span class="sxs-lookup"><span data-stu-id="bb4f5-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb4f5-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb4f5-113">Requirements</span></span>  
 <span data-ttu-id="bb4f5-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb4f5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb4f5-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb4f5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb4f5-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb4f5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb4f5-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb4f5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb4f5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb4f5-118">See also</span></span>

- [<span data-ttu-id="bb4f5-119">Enumerazione VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="bb4f5-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
- [<span data-ttu-id="bb4f5-120">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="bb4f5-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
