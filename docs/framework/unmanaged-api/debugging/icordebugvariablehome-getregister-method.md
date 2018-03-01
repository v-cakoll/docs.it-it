---
title: Metodo ICorDebugVariableHome::GetRegister
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 54f1c737b0c6ce6281a71419cbd8c88277702f41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="f215a-102">Metodo ICorDebugVariableHome::GetRegister</span><span class="sxs-lookup"><span data-stu-id="f215a-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="f215a-103">Ottiene il registro contenente una variabile con un tipo di posizione di `VLT_REGISTER`e la registrazione di base per una variabile con un tipo di posizione di `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="f215a-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f215a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f215a-104">Syntax</span></span>  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f215a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f215a-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="f215a-106">[out] Un valore di enumerazione CorDebugRegister che indica la registrazione per una variabile con un tipo di posizione di `VLT_REGISTER`e la registrazione di base per una variabile con un tipo di posizione di `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="f215a-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f215a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f215a-107">Return Value</span></span>  
 <span data-ttu-id="f215a-108">Il metodo restituisce i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="f215a-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="f215a-109">Valore</span><span class="sxs-lookup"><span data-stu-id="f215a-109">Value</span></span>|<span data-ttu-id="f215a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f215a-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="f215a-111">La variabile è il registro indicato dal `pRegister` argomento.</span><span class="sxs-lookup"><span data-stu-id="f215a-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="f215a-112">La variabile non è presente in un registro o un percorso relativo al registro.</span><span class="sxs-lookup"><span data-stu-id="f215a-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f215a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f215a-113">Requirements</span></span>  
 <span data-ttu-id="f215a-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f215a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f215a-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f215a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f215a-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f215a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f215a-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f215a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f215a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f215a-118">See Also</span></span>  
 [<span data-ttu-id="f215a-119">Enumerazione VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="f215a-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 [<span data-ttu-id="f215a-120">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="f215a-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
