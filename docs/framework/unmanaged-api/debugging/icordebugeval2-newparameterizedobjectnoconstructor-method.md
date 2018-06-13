---
title: Metodo ICorDebugEval2::NewParameterizedObjectNoConstructor
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObjectNoConstructor
helpviewer_keywords:
- NewParameterizedObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObjectNoConstructor method [.NET Framework debugging]
ms.assetid: f15b5b78-94f4-4eb9-b3b3-a621272f357c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aad5a285fc2280dc062b0f4cbb69977a7e605e9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412769"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="2a7a3-102">Metodo ICorDebugEval2::NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="2a7a3-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="2a7a3-103">Crea un'istanza di un nuovo oggetto di tipo con parametri della classe specificata senza tentare di chiamare un metodo del costruttore.</span><span class="sxs-lookup"><span data-stu-id="2a7a3-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a7a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a7a3-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a7a3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2a7a3-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="2a7a3-106">[in] Un puntatore a un oggetto ICorDebugClass che rappresenta la classe dell'oggetto deve essere creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="2a7a3-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="2a7a3-107">[in] Il numero di argomenti di tipo passato.</span><span class="sxs-lookup"><span data-stu-id="2a7a3-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="2a7a3-108">[in] Matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento di tipo per l'oggetto che viene creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="2a7a3-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a7a3-109">Note</span><span class="sxs-lookup"><span data-stu-id="2a7a3-109">Remarks</span></span>  
 <span data-ttu-id="2a7a3-110">Il `NewParameterizedObjectNoConstructor` metodo avrà esito negativo se un numero errato di argomenti di tipo o vengono passati i tipi di argomenti di tipo errati.</span><span class="sxs-lookup"><span data-stu-id="2a7a3-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a7a3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2a7a3-111">Requirements</span></span>  
 <span data-ttu-id="2a7a3-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a7a3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a7a3-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="2a7a3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a7a3-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2a7a3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a7a3-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a7a3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
