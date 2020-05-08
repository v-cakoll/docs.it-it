---
title: Metodo ICorDebugArrayValue::GetCount
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetCount
helpviewer_keywords:
- ICorDebugArrayValue::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 44cd98cf-2127-4d46-8c6a-da4e857bb6b0
topic_type:
- apiref
ms.openlocfilehash: 82f282630a2e31b8c67d43fa0f0b30431a0d6ee4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895051"
---
# <a name="icordebugarrayvaluegetcount-method"></a><span data-ttu-id="20667-102">Metodo ICorDebugArrayValue::GetCount</span><span class="sxs-lookup"><span data-stu-id="20667-102">ICorDebugArrayValue::GetCount Method</span></span>
<span data-ttu-id="20667-103">Ottiene il numero totale di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="20667-103">Gets the total number of elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20667-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20667-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20667-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="20667-105">Parameters</span></span>  
 `pnCount`  
 <span data-ttu-id="20667-106">out Puntatore al numero totale di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="20667-106">[out] A pointer to the total number of elements in the array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20667-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="20667-107">Requirements</span></span>  
 <span data-ttu-id="20667-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20667-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20667-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20667-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20667-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20667-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20667-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20667-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
