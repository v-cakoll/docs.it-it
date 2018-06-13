---
title: Metodo ICorDebugGenericValue::GetValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6d30a9f03d8717486be7cd89bb182d350a82df7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411636"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="48f75-102">Metodo ICorDebugGenericValue::GetValue</span><span class="sxs-lookup"><span data-stu-id="48f75-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="48f75-103">Copia il valore di questo oggetto generico nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="48f75-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48f75-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48f75-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48f75-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="48f75-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="48f75-106">[out] Puntatore al valore rappresentato dall'oggetto ICorDebugGenericValue.</span><span class="sxs-lookup"><span data-stu-id="48f75-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="48f75-107">Il valore può essere un tipo semplice o un tipo di riferimento (ovvero, un puntatore).</span><span class="sxs-lookup"><span data-stu-id="48f75-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48f75-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48f75-108">Requirements</span></span>  
 <span data-ttu-id="48f75-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48f75-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48f75-110">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="48f75-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48f75-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="48f75-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48f75-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48f75-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
