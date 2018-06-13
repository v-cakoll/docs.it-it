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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 184e578efb549a1dc2e9ec1e30a29ff289b68719
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411703"
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="a4df8-102">Metodo ICorDebugFunction::GetClass</span><span class="sxs-lookup"><span data-stu-id="a4df8-102">ICorDebugFunction::GetClass Method</span></span>
<span data-ttu-id="a4df8-103">Ottiene un oggetto ICorDebugClass che rappresenta la classe di che questa funzione è membro.</span><span class="sxs-lookup"><span data-stu-id="a4df8-103">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4df8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4df8-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a4df8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4df8-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="a4df8-106">[out] Un puntatore all'indirizzo del `ICorDebugClass` oggetto che rappresenta la classe, o null, se questa funzione non è un membro di una classe.</span><span class="sxs-lookup"><span data-stu-id="a4df8-106">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4df8-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a4df8-107">Requirements</span></span>  
 <span data-ttu-id="a4df8-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4df8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4df8-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a4df8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4df8-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a4df8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4df8-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4df8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
