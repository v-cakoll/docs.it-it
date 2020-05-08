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
ms.openlocfilehash: 7a52e61f41bd1d7f68523dd16f70010ffbba401e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895028"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="17efb-102">Metodo ICorDebugArrayValue::GetElement</span><span class="sxs-lookup"><span data-stu-id="17efb-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="17efb-103">Ottiene il valore dell'elemento di matrice specificato.</span><span class="sxs-lookup"><span data-stu-id="17efb-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17efb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17efb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17efb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="17efb-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="17efb-106">in Numero di dimensioni dell' `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="17efb-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="17efb-107">Questo valore corrisponde anche alla dimensione della `indices` matrice perché la relativa dimensione è uguale al numero di dimensioni dell' `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="17efb-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="17efb-108">in Matrice di valori di indice, ognuno dei quali specifica una posizione all'interno di una dimensione `ICorDebugArrayValue` dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="17efb-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="17efb-109">Questo valore non può essere null.</span><span class="sxs-lookup"><span data-stu-id="17efb-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="17efb-110">out Puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore dell'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="17efb-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17efb-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17efb-111">Requirements</span></span>  
 <span data-ttu-id="17efb-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17efb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17efb-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17efb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17efb-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17efb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17efb-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17efb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
