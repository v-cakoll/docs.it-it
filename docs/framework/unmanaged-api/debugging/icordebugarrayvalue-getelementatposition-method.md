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
ms.openlocfilehash: 10584442d7e0bd61e6decaf2b494dfe39f339d6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088422"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="d4d14-102">Metodo ICorDebugArrayValue::GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="d4d14-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="d4d14-103">Ottiene l'elemento in corrispondenza della posizione specificata, considerando la matrice come matrice unidimensionale in base zero.</span><span class="sxs-lookup"><span data-stu-id="d4d14-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4d14-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4d14-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4d14-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d4d14-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="d4d14-106">in Posizione dell'elemento da recuperare.</span><span class="sxs-lookup"><span data-stu-id="d4d14-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="d4d14-107">out Puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="d4d14-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4d14-108">Note</span><span class="sxs-lookup"><span data-stu-id="d4d14-108">Remarks</span></span>  
 <span data-ttu-id="d4d14-109">Il layout di una matrice MULTIDIMENSIONE segue lo C++ stile del layout della matrice.</span><span class="sxs-lookup"><span data-stu-id="d4d14-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4d14-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4d14-110">Requirements</span></span>  
 <span data-ttu-id="d4d14-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4d14-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4d14-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4d14-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4d14-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4d14-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4d14-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4d14-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
