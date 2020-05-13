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
ms.openlocfilehash: 7c64823e1a5c519eb74b508af093afeb1132e608
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210085"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="c2d72-102">Metodo ICorDebugReferenceValue::Dereference</span><span class="sxs-lookup"><span data-stu-id="c2d72-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="c2d72-103">Ottiene l'oggetto a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="c2d72-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2d72-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2d72-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2d72-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c2d72-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="c2d72-106">out Puntatore all'indirizzo di un ICorDebugValue che rappresenta l'oggetto a cui fa riferimento questo oggetto ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="c2d72-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2d72-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c2d72-107">Remarks</span></span>  
 <span data-ttu-id="c2d72-108">L' `ICorDebugValue` oggetto è valido solo se il relativo riferimento non è ancora stato disabilitato.</span><span class="sxs-lookup"><span data-stu-id="c2d72-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2d72-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2d72-109">Requirements</span></span>  
 <span data-ttu-id="c2d72-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2d72-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2d72-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2d72-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2d72-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2d72-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2d72-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2d72-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
