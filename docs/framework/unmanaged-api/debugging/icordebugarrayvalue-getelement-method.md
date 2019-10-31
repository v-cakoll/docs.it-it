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
ms.openlocfilehash: 3d45caae56403d77776f1a8adbb5fb9c368ff105
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088496"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="12a06-102">Metodo ICorDebugArrayValue::GetElement</span><span class="sxs-lookup"><span data-stu-id="12a06-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="12a06-103">Ottiene il valore dell'elemento di matrice specificato.</span><span class="sxs-lookup"><span data-stu-id="12a06-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12a06-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12a06-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]   
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12a06-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="12a06-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="12a06-106">in Numero di dimensioni dell'oggetto `ICorDebugArrayValue`.</span><span class="sxs-lookup"><span data-stu-id="12a06-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="12a06-107">Questo valore corrisponde anche alla dimensione della matrice `indices` perché la relativa dimensione è uguale al numero di dimensioni dell'oggetto `ICorDebugArrayValue`.</span><span class="sxs-lookup"><span data-stu-id="12a06-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="12a06-108">in Matrice di valori di indice, ognuno dei quali specifica una posizione all'interno di una dimensione dell'oggetto `ICorDebugArrayValue`.</span><span class="sxs-lookup"><span data-stu-id="12a06-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="12a06-109">Questo valore non può essere null.</span><span class="sxs-lookup"><span data-stu-id="12a06-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="12a06-110">out Puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore dell'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="12a06-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12a06-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="12a06-111">Requirements</span></span>  
 <span data-ttu-id="12a06-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12a06-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12a06-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12a06-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12a06-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12a06-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12a06-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12a06-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
