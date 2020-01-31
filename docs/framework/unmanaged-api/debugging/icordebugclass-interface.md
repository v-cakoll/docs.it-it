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
ms.openlocfilehash: 7ac588591222a1abbc7b99ec7e973284c055f95e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784160"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="657cb-102">Interfaccia ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="657cb-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="657cb-103">Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="657cb-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="657cb-104">Se il tipo è generico, `ICorDebugClass` rappresenta il tipo generico privo di istanze.</span><span class="sxs-lookup"><span data-stu-id="657cb-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="657cb-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="657cb-105">Methods</span></span>  
  
|<span data-ttu-id="657cb-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="657cb-106">Method</span></span>|<span data-ttu-id="657cb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="657cb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="657cb-108">Metodo GetModule</span><span class="sxs-lookup"><span data-stu-id="657cb-108">GetModule Method</span></span>](icordebugclass-getmodule-method.md)|<span data-ttu-id="657cb-109">Ottiene il modulo che definisce questa classe.</span><span class="sxs-lookup"><span data-stu-id="657cb-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="657cb-110">Metodo GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="657cb-110">GetStaticFieldValue Method</span></span>](icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="657cb-111">Ottiene il valore del campo statico specificato.</span><span class="sxs-lookup"><span data-stu-id="657cb-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="657cb-112">Metodo GetToken</span><span class="sxs-lookup"><span data-stu-id="657cb-112">GetToken Method</span></span>](icordebugclass-gettoken-method.md)|<span data-ttu-id="657cb-113">Ottiene il token di metadati `TypeDef` per questa classe.</span><span class="sxs-lookup"><span data-stu-id="657cb-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="657cb-114">Note</span><span class="sxs-lookup"><span data-stu-id="657cb-114">Remarks</span></span>  
 <span data-ttu-id="657cb-115">L'interfaccia `ICorDebugClass` rappresenta un tipo generico di cui non è stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="657cb-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="657cb-116">L'interfaccia ICorDebugType rappresenta un tipo generico di cui è stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="657cb-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="657cb-117">Ad esempio, `Hashtable<K, V>` viene rappresentata da `ICorDebugClass`, mentre `Hashtable<Int32, String>` viene rappresentata da `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="657cb-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="657cb-118">I tipi non generici sono rappresentati sia da `ICorDebugClass` che da `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="657cb-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="657cb-119">Quest'ultima interfaccia è stata introdotta nella versione .NET Framework 2,0 per gestire la creazione dell'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="657cb-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="657cb-120">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="657cb-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="657cb-121">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="657cb-121">Requirements</span></span>  
 <span data-ttu-id="657cb-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="657cb-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="657cb-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="657cb-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="657cb-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="657cb-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="657cb-125">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="657cb-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="657cb-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="657cb-126">See also</span></span>

- [<span data-ttu-id="657cb-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="657cb-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
