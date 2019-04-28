---
title: Metodo ICorDebugEval2::NewParameterizedObject
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c35baaee13782566c64dd8447c6a034f699b5cd0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667002"
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="a1cd1-102">Metodo ICorDebugEval2::NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="a1cd1-102">ICorDebugEval2::NewParameterizedObject Method</span></span>
<span data-ttu-id="a1cd1-103">Crea un'istanza di un nuovo oggetto di tipo con parametri e chiama il metodo costruttore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="a1cd1-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1cd1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1cd1-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1cd1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1cd1-105">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="a1cd1-106">[in] Un puntatore a un oggetto ICorDebugFunction che rappresenta il costruttore dell'oggetto da cui creare istanze.</span><span class="sxs-lookup"><span data-stu-id="a1cd1-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="a1cd1-107">[in] Il numero di argomenti tipo passati.</span><span class="sxs-lookup"><span data-stu-id="a1cd1-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="a1cd1-108">[in] Una matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento di tipo per l'oggetto che viene viene creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="a1cd1-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="a1cd1-109">[in] Il numero di argomenti passato al costruttore.</span><span class="sxs-lookup"><span data-stu-id="a1cd1-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="a1cd1-110">[in] Una matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugValue che rappresenta un valore dell'argomento passato al costruttore.</span><span class="sxs-lookup"><span data-stu-id="a1cd1-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1cd1-111">Note</span><span class="sxs-lookup"><span data-stu-id="a1cd1-111">Remarks</span></span>  
 <span data-ttu-id="a1cd1-112">Il costruttore dell'oggetto potrebbe richiedere <xref:System.Type> parametri.</span><span class="sxs-lookup"><span data-stu-id="a1cd1-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1cd1-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1cd1-113">Requirements</span></span>  
 <span data-ttu-id="a1cd1-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1cd1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1cd1-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1cd1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1cd1-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1cd1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1cd1-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1cd1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
