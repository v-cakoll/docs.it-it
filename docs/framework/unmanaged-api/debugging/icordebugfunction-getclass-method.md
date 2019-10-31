---
title: Metodo ICorDebugFunction::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetClass
helpviewer_keywords:
- GetClass method, ICorDebugFunction interface [.NET Framework debugging]
- ICorDebugFunction::GetClass method [.NET Framework debugging]
ms.assetid: 27967230-144f-40d3-9e23-961d0241abd9
topic_type:
- apiref
ms.openlocfilehash: 887d207aea3de9296107c041816606b2f5947406
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124026"
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="a685c-102">Metodo ICorDebugFunction::GetClass</span><span class="sxs-lookup"><span data-stu-id="a685c-102">ICorDebugFunction::GetClass Method</span></span>
<span data-ttu-id="a685c-103">Ottiene un oggetto ICorDebugClass che rappresenta la classe di cui questa funzione è membro.</span><span class="sxs-lookup"><span data-stu-id="a685c-103">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a685c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a685c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a685c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a685c-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="a685c-106">out Puntatore all'indirizzo del `ICorDebugClass` oggetto che rappresenta la classe, o null, se questa funzione non è un membro di una classe.</span><span class="sxs-lookup"><span data-stu-id="a685c-106">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a685c-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a685c-107">Requirements</span></span>  
 <span data-ttu-id="a685c-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a685c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a685c-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a685c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a685c-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a685c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a685c-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a685c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
