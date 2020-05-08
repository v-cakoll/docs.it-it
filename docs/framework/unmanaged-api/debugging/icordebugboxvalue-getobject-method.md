---
title: Metodo ICorDebugBoxValue::GetObject
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue::GetObject
helpviewer_keywords:
- ICorDebugBoxValue::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3a867a5b-bf94-493f-a4f5-b28685cf5325
topic_type:
- apiref
ms.openlocfilehash: 401f052b881c1a0cfa065ba60c93aca1706f34f4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894780"
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="1c61b-102">Metodo ICorDebugBoxValue::GetObject</span><span class="sxs-lookup"><span data-stu-id="1c61b-102">ICorDebugBoxValue::GetObject Method</span></span>
<span data-ttu-id="1c61b-103">Ottiene il valore boxed.</span><span class="sxs-lookup"><span data-stu-id="1c61b-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c61b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c61b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c61b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1c61b-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="1c61b-106">out Puntatore all'indirizzo di un oggetto ICorDebugObjectValue che rappresenta il valore boxed.</span><span class="sxs-lookup"><span data-stu-id="1c61b-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c61b-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c61b-107">Requirements</span></span>  
 <span data-ttu-id="1c61b-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c61b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c61b-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c61b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c61b-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c61b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c61b-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c61b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
