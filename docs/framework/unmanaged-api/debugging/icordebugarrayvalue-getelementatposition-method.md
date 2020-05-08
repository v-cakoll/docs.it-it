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
ms.openlocfilehash: 5644c20ec5df2606c7258131573691997f424e50
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895019"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="339f9-102">Metodo ICorDebugArrayValue::GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="339f9-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="339f9-103">Ottiene l'elemento in corrispondenza della posizione specificata, considerando la matrice come matrice unidimensionale in base zero.</span><span class="sxs-lookup"><span data-stu-id="339f9-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="339f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="339f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="339f9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="339f9-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="339f9-106">in Posizione dell'elemento da recuperare.</span><span class="sxs-lookup"><span data-stu-id="339f9-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="339f9-107">out Puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="339f9-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="339f9-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="339f9-108">Remarks</span></span>  
 <span data-ttu-id="339f9-109">Il layout di una matrice MULTIDIMENSIONE segue lo stile C++ del layout della matrice.</span><span class="sxs-lookup"><span data-stu-id="339f9-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="339f9-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="339f9-110">Requirements</span></span>  
 <span data-ttu-id="339f9-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="339f9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="339f9-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="339f9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="339f9-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="339f9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="339f9-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="339f9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
