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
ms.openlocfilehash: bc7d99d0ddb443cba227b7bad0cd53edb94c9101
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138545"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="495ce-102">Metodo ICorDebugHandleValue::GetHandleType</span><span class="sxs-lookup"><span data-stu-id="495ce-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="495ce-103">Ottiene un valore che indica il tipo di handle a cui fa riferimento questo oggetto ICorDebugHandleValue.</span><span class="sxs-lookup"><span data-stu-id="495ce-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="495ce-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="495ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="495ce-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="495ce-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="495ce-106">out Puntatore a un valore dell'enumerazione CorDebugHandleType che indica il tipo di questo handle.</span><span class="sxs-lookup"><span data-stu-id="495ce-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="495ce-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="495ce-107">Requirements</span></span>  
 <span data-ttu-id="495ce-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="495ce-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="495ce-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="495ce-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="495ce-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="495ce-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="495ce-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="495ce-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
