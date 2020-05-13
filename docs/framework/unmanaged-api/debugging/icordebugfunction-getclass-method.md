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
ms.openlocfilehash: 7a089831c39c36b0f8a0c7746e95a96e4ddfc5d9
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209396"
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="ea761-102">Metodo ICorDebugFunction::GetClass</span><span class="sxs-lookup"><span data-stu-id="ea761-102">ICorDebugFunction::GetClass Method</span></span>
<span data-ttu-id="ea761-103">Ottiene un oggetto ICorDebugClass che rappresenta la classe di cui questa funzione è membro.</span><span class="sxs-lookup"><span data-stu-id="ea761-103">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea761-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea761-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea761-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea761-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="ea761-106">out Puntatore all'indirizzo dell' `ICorDebugClass` oggetto che rappresenta la classe o null se questa funzione non è un membro di una classe.</span><span class="sxs-lookup"><span data-stu-id="ea761-106">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea761-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea761-107">Requirements</span></span>  
 <span data-ttu-id="ea761-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea761-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea761-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea761-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea761-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea761-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea761-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea761-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
