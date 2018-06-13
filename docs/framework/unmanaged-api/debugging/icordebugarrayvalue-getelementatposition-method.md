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
ms.openlocfilehash: 580c7b4dcd63f83e113a5317c242b7e66cfb3f5a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403416"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="79571-102">Metodo ICorDebugArrayValue::GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="79571-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="79571-103">Ottiene l'elemento in corrispondenza della posizione specificata, considerando la matrice come una matrice unidimensionale in base zero.</span><span class="sxs-lookup"><span data-stu-id="79571-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79571-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79571-104">Syntax</span></span>  
  
```  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79571-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="79571-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="79571-106">[in] La posizione dell'elemento da recuperare.</span><span class="sxs-lookup"><span data-stu-id="79571-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="79571-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="79571-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79571-108">Note</span><span class="sxs-lookup"><span data-stu-id="79571-108">Remarks</span></span>  
 <span data-ttu-id="79571-109">Il layout di una matrice multidimensionale segue lo stile C++ layout della matrice.</span><span class="sxs-lookup"><span data-stu-id="79571-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79571-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="79571-110">Requirements</span></span>  
 <span data-ttu-id="79571-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79571-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79571-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="79571-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79571-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="79571-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79571-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79571-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
