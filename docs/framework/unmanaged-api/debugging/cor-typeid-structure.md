---
title: Struttura COR_TYPEID
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ca6c9b3b02314843a3eaf01d8cd4a9eac5513efa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cortypeid-structure"></a><span data-ttu-id="e4205-102">Struttura COR_TYPEID</span><span class="sxs-lookup"><span data-stu-id="e4205-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="e4205-103">Contiene un identificatore di tipo.</span><span class="sxs-lookup"><span data-stu-id="e4205-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4205-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4205-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="e4205-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e4205-105">Members</span></span>  
  
|<span data-ttu-id="e4205-106">Membro</span><span class="sxs-lookup"><span data-stu-id="e4205-106">Member</span></span>|<span data-ttu-id="e4205-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4205-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="e4205-108">Il primo token.</span><span class="sxs-lookup"><span data-stu-id="e4205-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="e4205-109">Il secondo token.</span><span class="sxs-lookup"><span data-stu-id="e4205-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4205-110">Note</span><span class="sxs-lookup"><span data-stu-id="e4205-110">Remarks</span></span>  
 <span data-ttu-id="e4205-111">Il `COR_TYPEID` struttura viene restituita da una serie di metodi di debug che forniscono informazioni sugli oggetti da sottoporre a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="e4205-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="e4205-112">Può quindi essere passato come argomento ad altri metodi di debug che forniscono informazioni aggiuntive su tale elemento.</span><span class="sxs-lookup"><span data-stu-id="e4205-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="e4205-113">Ad esempio, enumerando un [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) dell'oggetto, è possibile recuperare singoli [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) gli oggetti che rappresentano i singoli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="e4205-113">For example, by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="e4205-114">È quindi possibile passare il `COR_TYPEID` valore il `COR_HEAPOBJECT.type` campo il [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) metodo per recuperare un oggetto ICorDebugType che fornisce informazioni sul tipo relative all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="e4205-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="e4205-115">Oggetto `COR_TYPEID` oggetto deve essere opaca.</span><span class="sxs-lookup"><span data-stu-id="e4205-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="e4205-116">I singoli campi non devono essere accessibile oppure modificati.</span><span class="sxs-lookup"><span data-stu-id="e4205-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="e4205-117">L'uso esclusivo è un identificatore che viene fornito come un `out` parametro in una chiamata al metodo e che può essere passato a sua volta, agli altri metodi per fornire informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="e4205-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4205-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e4205-118">Requirements</span></span>  
 <span data-ttu-id="e4205-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4205-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4205-120">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e4205-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4205-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4205-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4205-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4205-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4205-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4205-123">See Also</span></span>  
 [<span data-ttu-id="e4205-124">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="e4205-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="e4205-125">Debug</span><span class="sxs-lookup"><span data-stu-id="e4205-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
