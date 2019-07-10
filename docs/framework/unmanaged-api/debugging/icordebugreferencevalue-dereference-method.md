---
title: Metodo ICorDebugReferenceValue::Dereference
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2ea7ebff122622a0db46160d23574619664f8ad
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745029"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="853b1-102">Metodo ICorDebugReferenceValue::Dereference</span><span class="sxs-lookup"><span data-stu-id="853b1-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="853b1-103">Ottiene l'oggetto a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="853b1-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="853b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="853b1-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="853b1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="853b1-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="853b1-106">[out] Un puntatore all'indirizzo di un'interfaccia ICorDebugValue che rappresenta l'oggetto a cui fa riferimento questo oggetto ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="853b1-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="853b1-107">Note</span><span class="sxs-lookup"><span data-stu-id="853b1-107">Remarks</span></span>  
 <span data-ttu-id="853b1-108">Il `ICorDebugValue` oggetto è valido solo mentre il relativo riferimento non è ancora stato disabilitato.</span><span class="sxs-lookup"><span data-stu-id="853b1-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="853b1-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="853b1-109">Requirements</span></span>  
 <span data-ttu-id="853b1-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="853b1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="853b1-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="853b1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="853b1-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="853b1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="853b1-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="853b1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
