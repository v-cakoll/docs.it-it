---
title: Interfaccia ICorDebugClass
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e1ad830e728fbe764085a5808a48e4cacedc595
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133627"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="f7c12-102">Interfaccia ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="f7c12-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="f7c12-103">Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f7c12-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="f7c12-104">Se il tipo è generico, `ICorDebugClass` rappresenta il tipo generico privo di istanze.</span><span class="sxs-lookup"><span data-stu-id="f7c12-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f7c12-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="f7c12-105">Methods</span></span>  
  
|<span data-ttu-id="f7c12-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="f7c12-106">Method</span></span>|<span data-ttu-id="f7c12-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7c12-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f7c12-108">Metodo GetModule</span><span class="sxs-lookup"><span data-stu-id="f7c12-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="f7c12-109">Ottiene il modulo che definisce la classe.</span><span class="sxs-lookup"><span data-stu-id="f7c12-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="f7c12-110">Metodo GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="f7c12-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="f7c12-111">Ottiene il valore del campo statico specificato.</span><span class="sxs-lookup"><span data-stu-id="f7c12-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="f7c12-112">Metodo GetToken</span><span class="sxs-lookup"><span data-stu-id="f7c12-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="f7c12-113">Ottiene il `TypeDef` token di metadati per questa classe.</span><span class="sxs-lookup"><span data-stu-id="f7c12-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7c12-114">Note</span><span class="sxs-lookup"><span data-stu-id="f7c12-114">Remarks</span></span>  
 <span data-ttu-id="f7c12-115">Il `ICorDebugClass` interfaccia rappresenta un tipo generico privo di istanze.</span><span class="sxs-lookup"><span data-stu-id="f7c12-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="f7c12-116">L'interfaccia ICorDebugType rappresenta un tipo generico con istanze.</span><span class="sxs-lookup"><span data-stu-id="f7c12-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="f7c12-117">Ad esempio, `Hashtable<K, V>` sarebbe rappresentato da `ICorDebugClass`, mentre `Hashtable<Int32, String>` sarebbe rappresentato da `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="f7c12-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="f7c12-118">I tipi non generici sono rappresentati da entrambi `ICorDebugClass` e `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="f7c12-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="f7c12-119">L'interfaccia di quest'ultima è stato introdotto in .NET Framework versione 2.0 per gestire la creazione di istanze di tipo.</span><span class="sxs-lookup"><span data-stu-id="f7c12-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7c12-120">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="f7c12-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7c12-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7c12-121">Requirements</span></span>  
 <span data-ttu-id="f7c12-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7c12-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7c12-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7c12-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7c12-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7c12-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7c12-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7c12-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c12-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7c12-126">See also</span></span>

- [<span data-ttu-id="f7c12-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f7c12-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
