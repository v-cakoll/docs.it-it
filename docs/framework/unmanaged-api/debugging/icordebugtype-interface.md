---
title: Interfaccia ICorDebugType
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74863af1096f8600b8095e593c1f3c820c512e9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166803"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="534b0-102">Interfaccia ICorDebugType</span><span class="sxs-lookup"><span data-stu-id="534b0-102">ICorDebugType Interface</span></span>
<span data-ttu-id="534b0-103">Rappresenta un tipo di base o complesso (che è, definita dall'utente).</span><span class="sxs-lookup"><span data-stu-id="534b0-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="534b0-104">Se il tipo è generico, `ICorDebugType` rappresenta il tipo generico di cui è stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="534b0-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="534b0-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="534b0-105">Methods</span></span>  
  
|<span data-ttu-id="534b0-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="534b0-106">Method</span></span>|<span data-ttu-id="534b0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="534b0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="534b0-108">Metodo EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="534b0-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="534b0-109">Ottiene un puntatore a interfaccia a un'interfaccia ICorDebugTypeEnum che fa riferimento il tipo generico <xref:System.Type> parametri della classe a cui fa riferimento `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="534b0-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="534b0-110">Metodo GetBase</span><span class="sxs-lookup"><span data-stu-id="534b0-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="534b0-111">Ottiene un puntatore a interfaccia a un `ICorDebugType` che fa riferimento la classe di base della classe a cui fa riferimento `ICorDebugType`, se presente.</span><span class="sxs-lookup"><span data-stu-id="534b0-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="534b0-112">Metodo GetClass</span><span class="sxs-lookup"><span data-stu-id="534b0-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="534b0-113">Ottiene un puntatore a interfaccia ICorDebugClass che fa riferimento al costruttore dell'oggetto tipizzato `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="534b0-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="534b0-114">Metodo GetFirstTypeParameter</span><span class="sxs-lookup"><span data-stu-id="534b0-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="534b0-115">Ottiene un puntatore a interfaccia a un `ICorDebugType` che fa riferimento il primo tipo generico <xref:System.Type> parametro per il costruttore della classe a cui fa riferimento `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="534b0-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="534b0-116">Metodo GetRank</span><span class="sxs-lookup"><span data-stu-id="534b0-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="534b0-117">Ottiene il numero di dimensioni in un tipo di matrice.</span><span class="sxs-lookup"><span data-stu-id="534b0-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="534b0-118">Metodo GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="534b0-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="534b0-119">Ottiene un puntatore a interfaccia a ICorDebugValue che contiene il valore del campo statico a cui fa riferimento il campo specificato token lo stack frame specificato.</span><span class="sxs-lookup"><span data-stu-id="534b0-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="534b0-120">Metodo GetType</span><span class="sxs-lookup"><span data-stu-id="534b0-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="534b0-121">Ottiene un valore CorElementType che descrive il tipo nativo del common language runtime <xref:System.Type> fa riferimento questo `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="534b0-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="534b0-122">Note</span><span class="sxs-lookup"><span data-stu-id="534b0-122">Remarks</span></span>  
 <span data-ttu-id="534b0-123">Se il tipo è generico, `ICorDebugClass` rappresenta il tipo privo di istanze.</span><span class="sxs-lookup"><span data-stu-id="534b0-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="534b0-124">Il `ICorDebugType` interfaccia rappresenta un tipo generico con istanze.</span><span class="sxs-lookup"><span data-stu-id="534b0-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="534b0-125">Ad esempio, Hashtable\<K, V > viene rappresentato da `ICorDebugClass`, mentre Hashtable\<Int32, String > sarebbe rappresentato da `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="534b0-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="534b0-126">I tipi non generici sono rappresentati da entrambi `ICorDebugClass` e `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="534b0-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="534b0-127">L'interfaccia di quest'ultima è stato introdotto in .NET Framework versione 2.0 per gestire la creazione di istanze di tipo.</span><span class="sxs-lookup"><span data-stu-id="534b0-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="534b0-128">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="534b0-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="534b0-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="534b0-129">Requirements</span></span>  
 <span data-ttu-id="534b0-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="534b0-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="534b0-131">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="534b0-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="534b0-132">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="534b0-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="534b0-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="534b0-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="534b0-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="534b0-134">See also</span></span>

- [<span data-ttu-id="534b0-135">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="534b0-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
