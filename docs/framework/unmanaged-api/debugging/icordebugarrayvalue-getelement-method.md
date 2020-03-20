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
ms.openlocfilehash: adcb7b5a27f3b8c63dbbb660a23b5c891f84ac46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179014"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="f298a-102">Metodo ICorDebugArrayValue::GetElement</span><span class="sxs-lookup"><span data-stu-id="f298a-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="f298a-103">Ottiene il valore dell'elemento della matrice specificato.</span><span class="sxs-lookup"><span data-stu-id="f298a-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f298a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f298a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f298a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f298a-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="f298a-106">[in] Numero di dimensioni `ICorDebugArrayValue` di questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="f298a-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="f298a-107">Questo valore è anche `indices` la dimensione della matrice perché la sua `ICorDebugArrayValue` dimensione è uguale al numero di dimensioni dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f298a-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="f298a-108">[in] Matrice di valori di indice, ognuno dei quali `ICorDebugArrayValue` specifica una posizione all'interno di una dimensione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f298a-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="f298a-109">Questo valore non deve essere null.</span><span class="sxs-lookup"><span data-stu-id="f298a-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f298a-110">[fuori] Puntatore all'indirizzo di un ICorDebugValue oggetto che rappresenta il valore dell'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="f298a-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f298a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f298a-111">Requirements</span></span>  
 <span data-ttu-id="f298a-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f298a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f298a-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f298a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f298a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f298a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f298a-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f298a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
