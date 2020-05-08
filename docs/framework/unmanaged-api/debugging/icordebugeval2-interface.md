---
title: Interfaccia ICorDebugEval2
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
ms.openlocfilehash: b597d95b5b25e5ebf04fac48e4f3fda312a9594c
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976122"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="0ebf1-102">Interfaccia ICorDebugEval2</span><span class="sxs-lookup"><span data-stu-id="0ebf1-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="0ebf1-103">Estende "ICorDebugEval" per fornire supporto per i tipi generici.</span><span class="sxs-lookup"><span data-stu-id="0ebf1-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ebf1-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0ebf1-104">Methods</span></span>  
  
|<span data-ttu-id="0ebf1-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0ebf1-105">Method</span></span>|<span data-ttu-id="0ebf1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ebf1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ebf1-107">Metodo CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="0ebf1-107">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="0ebf1-108">Imposta una chiamata all'oggetto "ICorDebugFunction" specificato, che può essere annidato all'interno di un tipo il cui costruttore accetta parametri di tipo oppure accetta parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="0ebf1-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="0ebf1-109">Metodo CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="0ebf1-109">CreateValueForType Method</span></span>](icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="0ebf1-110">Ottiene un puntatore a un nuovo oggetto "ICorDebugValue" del tipo specificato, con un valore iniziale null o zero.</span><span class="sxs-lookup"><span data-stu-id="0ebf1-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="0ebf1-111">Metodo NewParameterizedArray</span><span class="sxs-lookup"><span data-stu-id="0ebf1-111">NewParameterizedArray Method</span></span>](icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="0ebf1-112">Alloca una nuova matrice del tipo e delle dimensioni dell'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="0ebf1-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="0ebf1-113">Metodo NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="0ebf1-113">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="0ebf1-114">Crea un'istanza di un nuovo oggetto di tipo con parametri e chiama il metodo del costruttore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="0ebf1-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="0ebf1-115">Metodo NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="0ebf1-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="0ebf1-116">Crea un'istanza di un nuovo oggetto di tipo con parametri della classe specificata senza provare a chiamare un metodo del costruttore</span><span class="sxs-lookup"><span data-stu-id="0ebf1-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="0ebf1-117">Metodo NewStringWithLength</span><span class="sxs-lookup"><span data-stu-id="0ebf1-117">NewStringWithLength Method</span></span>](icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="0ebf1-118">Crea una nuova stringa della lunghezza specificata con il contenuto specificato.</span><span class="sxs-lookup"><span data-stu-id="0ebf1-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="0ebf1-119">Metodo RudeAbort</span><span class="sxs-lookup"><span data-stu-id="0ebf1-119">RudeAbort Method</span></span>](icordebugeval2-rudeabort-method.md)|<span data-ttu-id="0ebf1-120">Interrompe il calcolo `ICorDebugEval2` attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0ebf1-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ebf1-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0ebf1-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ebf1-122">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="0ebf1-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ebf1-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ebf1-123">Requirements</span></span>  
 <span data-ttu-id="0ebf1-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ebf1-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ebf1-125">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ebf1-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ebf1-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ebf1-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ebf1-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ebf1-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ebf1-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ebf1-128">See also</span></span>

- [<span data-ttu-id="0ebf1-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0ebf1-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
