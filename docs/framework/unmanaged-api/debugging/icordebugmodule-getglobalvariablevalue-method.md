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
ms.openlocfilehash: 00e747e43f67533771665313f4d420e4725945cd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485352"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="4f5a4-102">Metodo ICorDebugModule::GetGlobalVariableValue</span><span class="sxs-lookup"><span data-stu-id="4f5a4-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>
<span data-ttu-id="4f5a4-103">Ottiene il valore della variabile globale specificata.</span><span class="sxs-lookup"><span data-stu-id="4f5a4-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f5a4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f5a4-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f5a4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f5a4-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="4f5a4-106">[in] Un `mdFieldDef` token che fa riferimento a metadati che descrivono la variabile globale.</span><span class="sxs-lookup"><span data-stu-id="4f5a4-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="4f5a4-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore della variabile globale specificata.</span><span class="sxs-lookup"><span data-stu-id="4f5a4-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f5a4-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f5a4-108">Requirements</span></span>  
 <span data-ttu-id="4f5a4-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f5a4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f5a4-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f5a4-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f5a4-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f5a4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f5a4-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f5a4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
