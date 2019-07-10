---
title: Metodo ICorDebugHandleValue::GetHandleType
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.GetHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::GetHandleType
helpviewer_keywords:
- GetHandleType method [.NET Framework debugging]
- ICorDebugHandleValue::GetHandleType method [.NET Framework debugging]
ms.assetid: d5e7b12d-835a-4e86-ae2f-d658d4f1c67c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0bc65cdeada059f6e9b41dc8eb4d7589a232143d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756832"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="21861-102">Metodo ICorDebugHandleValue::GetHandleType</span><span class="sxs-lookup"><span data-stu-id="21861-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="21861-103">Ottiene un valore che indica il tipo di handle fa riferimento questo oggetto ICorDebugHandleValue.</span><span class="sxs-lookup"><span data-stu-id="21861-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21861-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21861-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21861-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="21861-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="21861-106">[out] Puntatore a un valore dell'enumerazione CorDebugHandleType che indica il tipo di questo handle.</span><span class="sxs-lookup"><span data-stu-id="21861-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21861-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="21861-107">Requirements</span></span>  
 <span data-ttu-id="21861-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21861-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21861-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21861-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21861-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21861-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21861-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21861-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
