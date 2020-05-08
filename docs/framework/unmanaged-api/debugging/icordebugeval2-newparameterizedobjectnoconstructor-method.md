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
ms.openlocfilehash: 90fce1710f97341fb49be1d07f7af2edf8cb848c
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976083"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="469ec-102">Metodo ICorDebugEval2::NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="469ec-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="469ec-103">Crea un'istanza di un nuovo oggetto di tipo con parametri della classe specificata senza provare a chiamare un metodo del costruttore.</span><span class="sxs-lookup"><span data-stu-id="469ec-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="469ec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="469ec-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="469ec-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="469ec-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="469ec-106">in Puntatore a un oggetto ICorDebugClass che rappresenta la classe dell'oggetto di cui creare un'istanza.</span><span class="sxs-lookup"><span data-stu-id="469ec-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="469ec-107">in Numero di argomenti di tipo passati.</span><span class="sxs-lookup"><span data-stu-id="469ec-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="469ec-108">in Matrice di puntatori, ciascuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento di tipo per l'oggetto di cui viene creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="469ec-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="469ec-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="469ec-109">Remarks</span></span>  
 <span data-ttu-id="469ec-110">Il `NewParameterizedObjectNoConstructor` metodo avrà esito negativo se viene passato un numero errato di argomenti di tipo o tipi non corretti di argomenti di tipo.</span><span class="sxs-lookup"><span data-stu-id="469ec-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="469ec-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="469ec-111">Requirements</span></span>  
 <span data-ttu-id="469ec-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="469ec-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="469ec-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="469ec-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="469ec-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="469ec-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="469ec-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="469ec-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
