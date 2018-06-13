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
ms.openlocfilehash: 51fd8e9728955e8f426a38b8bf6cdc78dfa9bbde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412347"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="0f095-102">Metodo ICorDebugHandleValue::GetHandleType</span><span class="sxs-lookup"><span data-stu-id="0f095-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="0f095-103">Ottiene un valore che indica il tipo di handle a cui fa riferimento l'oggetto ICorDebugHandleValue.</span><span class="sxs-lookup"><span data-stu-id="0f095-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f095-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f095-104">Syntax</span></span>  
  
```  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f095-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0f095-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="0f095-106">[out] Un puntatore a un valore di enumerazione CorDebugHandleType che indica il tipo di questo handle.</span><span class="sxs-lookup"><span data-stu-id="0f095-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f095-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0f095-107">Requirements</span></span>  
 <span data-ttu-id="0f095-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f095-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f095-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0f095-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f095-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0f095-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f095-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f095-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
