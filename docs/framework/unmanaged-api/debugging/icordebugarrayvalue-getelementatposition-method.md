---
title: Metodo ICorDebugArrayValue::GetElementAtPosition
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementAtPosition
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementAtPosition
helpviewer_keywords:
- GetElementAtPosition method [.NET Framework debugging]
- ICorDebugArrayValue::GetElementAtPosition method [.NET Framework debugging]
ms.assetid: 6fd5eaa4-1997-4910-82f5-3887480db764
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76100116f2ca3a9b9a99477ca2352d5fa1335ab2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502254"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="67807-102">Metodo ICorDebugArrayValue::GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="67807-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="67807-103">Ottiene l'elemento in corrispondenza della posizione specificata, considerando la matrice come una matrice unidimensionale in base zero.</span><span class="sxs-lookup"><span data-stu-id="67807-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67807-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67807-104">Syntax</span></span>  
  
```  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67807-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="67807-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="67807-106">[in] La posizione dell'elemento da recuperare.</span><span class="sxs-lookup"><span data-stu-id="67807-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="67807-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="67807-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67807-108">Note</span><span class="sxs-lookup"><span data-stu-id="67807-108">Remarks</span></span>  
 <span data-ttu-id="67807-109">Il layout di una matrice multidimensionale segue lo stile C++ del layout della matrice.</span><span class="sxs-lookup"><span data-stu-id="67807-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67807-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="67807-110">Requirements</span></span>  
 <span data-ttu-id="67807-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67807-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67807-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67807-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67807-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67807-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67807-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67807-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
