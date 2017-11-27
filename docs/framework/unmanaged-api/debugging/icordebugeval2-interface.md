---
title: ICorDebugEval2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2
helpviewer_keywords: ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fbcf36ff7aca84299c55083b4ae135ce0a9ec4f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2-interface1"></a><span data-ttu-id="f6288-102">ICorDebugEval2 Interface1</span><span class="sxs-lookup"><span data-stu-id="f6288-102">ICorDebugEval2 Interface1</span></span>
<span data-ttu-id="f6288-103">Estende "ICorDebugEval" per fornire il supporto per i tipi generici.</span><span class="sxs-lookup"><span data-stu-id="f6288-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f6288-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f6288-104">Methods</span></span>  
  
|<span data-ttu-id="f6288-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f6288-105">Method</span></span>|<span data-ttu-id="f6288-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6288-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6288-107">CallParameterizedFunction (metodo)</span><span class="sxs-lookup"><span data-stu-id="f6288-107">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="f6288-108">Imposta una chiamata all'oggetto specificato "ICorDebugFunction", che può essere annidata all'interno di un tipo il cui costruttore accetta parametri di tipo, o che può accettare direttamente i parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="f6288-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="f6288-109">CreateValueForType (metodo)</span><span class="sxs-lookup"><span data-stu-id="f6288-109">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="f6288-110">Ottiene un puntatore a un nuovo "ICorDebugValue" del tipo specificato, con un valore iniziale pari a zero o null.</span><span class="sxs-lookup"><span data-stu-id="f6288-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="f6288-111">NewParameterizedArray (metodo)</span><span class="sxs-lookup"><span data-stu-id="f6288-111">NewParameterizedArray Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="f6288-112">Alloca una nuova matrice del tipo di elemento specificato e le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="f6288-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="f6288-113">NewParameterizedObject (metodo)</span><span class="sxs-lookup"><span data-stu-id="f6288-113">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="f6288-114">Crea un nuovo oggetto di tipo con parametri e chiama il metodo costruttore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f6288-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="f6288-115">NewParameterizedObjectNoConstructor (metodo)</span><span class="sxs-lookup"><span data-stu-id="f6288-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="f6288-116">Crea un nuovo oggetto di tipo con parametri della classe specificata senza tentare di chiamare un metodo del costruttore</span><span class="sxs-lookup"><span data-stu-id="f6288-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="f6288-117">NewStringWithLength (metodo)</span><span class="sxs-lookup"><span data-stu-id="f6288-117">NewStringWithLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="f6288-118">Crea una nuova stringa di lunghezza specificata con il contenuto specificato.</span><span class="sxs-lookup"><span data-stu-id="f6288-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="f6288-119">RudeAbort (metodo)</span><span class="sxs-lookup"><span data-stu-id="f6288-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|<span data-ttu-id="f6288-120">Interrompe il calcolo da questo `ICorDebugEval2` attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f6288-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6288-121">Note</span><span class="sxs-lookup"><span data-stu-id="f6288-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6288-122">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="f6288-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6288-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f6288-123">Requirements</span></span>  
 <span data-ttu-id="f6288-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6288-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6288-125">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f6288-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6288-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6288-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6288-127">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6288-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6288-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6288-128">See Also</span></span>  
 [<span data-ttu-id="f6288-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f6288-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
