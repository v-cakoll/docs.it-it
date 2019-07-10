---
title: Metodo ICorDebugModule::GetGlobalVariableValue
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetGlobalVariableValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetGlobalVariableValue
helpviewer_keywords:
- ICorDebugModule::GetGlobalVariableValue method [.NET Framework debugging]
- GetGlobalVariableValue method [.NET Framework debugging]
ms.assetid: bbc0881c-6a59-41a0-b5ee-2f3d1b71684c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd79299dcfdb03b703c2cab214ba448631daa6f2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763489"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="5e711-102">Metodo ICorDebugModule::GetGlobalVariableValue</span><span class="sxs-lookup"><span data-stu-id="5e711-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>
<span data-ttu-id="5e711-103">Ottiene il valore della variabile globale specificata.</span><span class="sxs-lookup"><span data-stu-id="5e711-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e711-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e711-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e711-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5e711-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="5e711-106">[in] Un `mdFieldDef` token che fa riferimento a metadati che descrivono la variabile globale.</span><span class="sxs-lookup"><span data-stu-id="5e711-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="5e711-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore della variabile globale specificata.</span><span class="sxs-lookup"><span data-stu-id="5e711-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e711-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5e711-108">Requirements</span></span>  
 <span data-ttu-id="5e711-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e711-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e711-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e711-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e711-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e711-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e711-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e711-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
