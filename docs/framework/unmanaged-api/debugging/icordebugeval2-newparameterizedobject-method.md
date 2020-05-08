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
ms.openlocfilehash: f6ede42ac90f65f934e285f879bcef62d13b65cb
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976096"
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="c095a-102">Metodo ICorDebugEval2::NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="c095a-102">ICorDebugEval2::NewParameterizedObject Method</span></span>
<span data-ttu-id="c095a-103">Crea un'istanza di un nuovo oggetto di tipo con parametri e chiama il metodo del costruttore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c095a-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c095a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c095a-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c095a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c095a-105">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="c095a-106">in Puntatore a un oggetto ICorDebugFunction che rappresenta il costruttore dell'oggetto di cui creare un'istanza.</span><span class="sxs-lookup"><span data-stu-id="c095a-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="c095a-107">in Numero di argomenti di tipo passati.</span><span class="sxs-lookup"><span data-stu-id="c095a-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="c095a-108">in Matrice di puntatori, ciascuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento di tipo per l'oggetto di cui viene creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="c095a-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="c095a-109">in Numero di argomenti passati al costruttore.</span><span class="sxs-lookup"><span data-stu-id="c095a-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="c095a-110">in Matrice di puntatori, ciascuno dei quali punta a un oggetto ICorDebugValue che rappresenta un valore di argomento passato al costruttore.</span><span class="sxs-lookup"><span data-stu-id="c095a-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c095a-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c095a-111">Remarks</span></span>  
 <span data-ttu-id="c095a-112">Il costruttore dell'oggetto può assumere <xref:System.Type> parametri.</span><span class="sxs-lookup"><span data-stu-id="c095a-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c095a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c095a-113">Requirements</span></span>  
 <span data-ttu-id="c095a-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c095a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c095a-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c095a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c095a-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c095a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c095a-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c095a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
