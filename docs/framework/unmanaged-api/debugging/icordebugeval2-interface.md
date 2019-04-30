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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3767368c9da8c97cd081787c0945a15552a1da46
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995969"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="14e66-102">Interfaccia ICorDebugEval2</span><span class="sxs-lookup"><span data-stu-id="14e66-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="14e66-103">Estende "ICorDebugEval" per fornire supporto per i tipi generici.</span><span class="sxs-lookup"><span data-stu-id="14e66-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="14e66-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="14e66-104">Methods</span></span>  
  
|<span data-ttu-id="14e66-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="14e66-105">Method</span></span>|<span data-ttu-id="14e66-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14e66-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14e66-107">Metodo CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="14e66-107">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="14e66-108">Imposta una chiamata all'oggetto specificato "ICorDebugFunction", che possono essere annidate all'interno di un tipo il cui costruttore accetta parametri di tipo oppure può accettare direttamente i parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="14e66-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="14e66-109">Metodo CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="14e66-109">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="14e66-110">Ottiene un puntatore a un nuovo "ICorDebugValue" del tipo specificato, con un valore iniziale pari a zero o null.</span><span class="sxs-lookup"><span data-stu-id="14e66-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="14e66-111">Metodo NewParameterizedArray</span><span class="sxs-lookup"><span data-stu-id="14e66-111">NewParameterizedArray Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="14e66-112">Consente di allocare una nuova matrice del tipo di elemento specificato e le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="14e66-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="14e66-113">Metodo NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="14e66-113">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="14e66-114">Crea un'istanza di un nuovo oggetto di tipo con parametri e chiama il metodo costruttore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="14e66-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="14e66-115">Metodo NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="14e66-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="14e66-116">Crea un'istanza di un nuovo oggetto di tipo con parametri della classe specificata senza effettuare alcun tentativo di chiamare un metodo del costruttore</span><span class="sxs-lookup"><span data-stu-id="14e66-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="14e66-117">Metodo NewStringWithLength</span><span class="sxs-lookup"><span data-stu-id="14e66-117">NewStringWithLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="14e66-118">Crea una nuova stringa di lunghezza specificata con il contenuto specificato.</span><span class="sxs-lookup"><span data-stu-id="14e66-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="14e66-119">Metodo RudeAbort</span><span class="sxs-lookup"><span data-stu-id="14e66-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|<span data-ttu-id="14e66-120">Interrompe il calcolo da questo `ICorDebugEval2` attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="14e66-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14e66-121">Note</span><span class="sxs-lookup"><span data-stu-id="14e66-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14e66-122">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="14e66-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14e66-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="14e66-123">Requirements</span></span>  
 <span data-ttu-id="14e66-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14e66-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14e66-125">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14e66-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14e66-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14e66-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14e66-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14e66-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14e66-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14e66-128">See also</span></span>

- [<span data-ttu-id="14e66-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="14e66-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
