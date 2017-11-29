---
title: Metodo ICorDebugVariableHome::GetRegister
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetRegister
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f16e4bfe4767e1b49d7dacf0481e8911a90e178
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="08311-102">Metodo ICorDebugVariableHome::GetRegister</span><span class="sxs-lookup"><span data-stu-id="08311-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="08311-103">Ottiene il registro contenente una variabile con un tipo di posizione di `VLT_REGISTER`e la registrazione di base per una variabile con un tipo di posizione di `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="08311-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08311-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08311-104">Syntax</span></span>  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08311-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="08311-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="08311-106">[out] Un valore di enumerazione CorDebugRegister che indica la registrazione per una variabile con un tipo di posizione di `VLT_REGISTER`e la registrazione di base per una variabile con un tipo di posizione di `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="08311-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08311-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="08311-107">Return Value</span></span>  
 <span data-ttu-id="08311-108">Il metodo restituisce i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="08311-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="08311-109">Valore</span><span class="sxs-lookup"><span data-stu-id="08311-109">Value</span></span>|<span data-ttu-id="08311-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08311-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="08311-111">La variabile è il registro indicato dal `pRegister` argomento.</span><span class="sxs-lookup"><span data-stu-id="08311-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="08311-112">La variabile non è presente in un registro o un percorso relativo al registro.</span><span class="sxs-lookup"><span data-stu-id="08311-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="08311-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08311-113">Requirements</span></span>  
 <span data-ttu-id="08311-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08311-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08311-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="08311-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08311-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08311-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08311-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08311-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08311-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08311-118">See Also</span></span>  
 [<span data-ttu-id="08311-119">Enumerazione VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="08311-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 [<span data-ttu-id="08311-120">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="08311-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
