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
ms.openlocfilehash: 770a9280d27c84b950e00e71328c9b28e61c9e7c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084813"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="87397-102">Metodo ICorDebugEval2::NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="87397-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="87397-103">Crea un'istanza di un nuovo oggetto di tipo con parametri della classe specificata senza provare a chiamare un metodo del costruttore.</span><span class="sxs-lookup"><span data-stu-id="87397-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87397-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87397-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87397-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="87397-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="87397-106">in Puntatore a un oggetto ICorDebugClass che rappresenta la classe dell'oggetto di cui creare un'istanza.</span><span class="sxs-lookup"><span data-stu-id="87397-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="87397-107">in Numero di argomenti di tipo passati.</span><span class="sxs-lookup"><span data-stu-id="87397-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="87397-108">in Matrice di puntatori, ciascuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento di tipo per l'oggetto di cui viene creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="87397-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87397-109">Note</span><span class="sxs-lookup"><span data-stu-id="87397-109">Remarks</span></span>  
 <span data-ttu-id="87397-110">Il metodo `NewParameterizedObjectNoConstructor` avrà esito negativo se viene passato un numero errato di argomenti di tipo o tipi non corretti di argomenti di tipo.</span><span class="sxs-lookup"><span data-stu-id="87397-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87397-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87397-111">Requirements</span></span>  
 <span data-ttu-id="87397-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87397-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87397-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87397-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87397-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87397-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87397-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87397-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
