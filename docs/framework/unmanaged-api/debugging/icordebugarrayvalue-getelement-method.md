---
title: Metodo ICorDebugArrayValue::GetElement
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElement
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 356f7ec9c50ce511883cbf0f5fbcb729493c92af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737577"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="97984-102">Metodo ICorDebugArrayValue::GetElement</span><span class="sxs-lookup"><span data-stu-id="97984-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="97984-103">Ottiene il valore dell'elemento della matrice specificata.</span><span class="sxs-lookup"><span data-stu-id="97984-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97984-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97984-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]   
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97984-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="97984-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="97984-106">[in] Il numero di dimensioni di questo `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="97984-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="97984-107">Questo valore viene anche le dimensioni dei `indices` matrice perché la dimensione è uguale al numero di dimensioni del `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="97984-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="97984-108">[in] Una matrice di valori di indice, ognuno dei quali specifica una posizione all'interno di una dimensione del `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="97984-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="97984-109">Questo valore non deve essere null.</span><span class="sxs-lookup"><span data-stu-id="97984-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="97984-110">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore dell'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="97984-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97984-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97984-111">Requirements</span></span>  
 <span data-ttu-id="97984-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97984-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97984-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97984-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97984-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97984-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97984-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97984-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
