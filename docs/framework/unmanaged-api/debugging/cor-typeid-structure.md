---
title: Struttura COR_TYPEID
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51104516008ffee0694c72733cb5f82b5ba6d8cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609456"
---
# <a name="cortypeid-structure"></a><span data-ttu-id="f681f-102">Struttura COR_TYPEID</span><span class="sxs-lookup"><span data-stu-id="f681f-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="f681f-103">Contiene un identificatore di tipo.</span><span class="sxs-lookup"><span data-stu-id="f681f-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f681f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f681f-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="f681f-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f681f-105">Members</span></span>  
  
|<span data-ttu-id="f681f-106">Member</span><span class="sxs-lookup"><span data-stu-id="f681f-106">Member</span></span>|<span data-ttu-id="f681f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f681f-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="f681f-108">Il primo token.</span><span class="sxs-lookup"><span data-stu-id="f681f-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="f681f-109">Secondo token.</span><span class="sxs-lookup"><span data-stu-id="f681f-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f681f-110">Note</span><span class="sxs-lookup"><span data-stu-id="f681f-110">Remarks</span></span>  
 <span data-ttu-id="f681f-111">Il `COR_TYPEID` struttura viene restituita da un numero di metodi di debug che forniscono informazioni sugli oggetti di essere sottoposto a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="f681f-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="f681f-112">Si può quindi essere passato come argomento per altri metodi di debug che forniscono informazioni aggiuntive relative a tale elemento.</span><span class="sxs-lookup"><span data-stu-id="f681f-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="f681f-113">Ad esempio, tramite l'enumerazione un' [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) dell'oggetto, è possibile recuperare singoli [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) gli oggetti che rappresentano singoli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="f681f-113">For example, by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="f681f-114">È quindi possibile passare il `COR_TYPEID` valore di `COR_HEAPOBJECT.type` campo il [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) metodo per recuperare un oggetto ICorDebugType che fornisce informazioni sul tipo sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f681f-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="f681f-115">Oggetto `COR_TYPEID` oggetto deve essere opaca.</span><span class="sxs-lookup"><span data-stu-id="f681f-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="f681f-116">I singoli campi non devono essere accessibile o modificati.</span><span class="sxs-lookup"><span data-stu-id="f681f-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="f681f-117">L'utilizzo esclusivo è un identificatore che viene fornito come un `out` parametro in una chiamata al metodo e che può essere passato a sua volta, agli altri metodi per fornire informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="f681f-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f681f-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f681f-118">Requirements</span></span>  
 <span data-ttu-id="f681f-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f681f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f681f-120">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f681f-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f681f-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f681f-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f681f-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f681f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f681f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f681f-123">See also</span></span>

- [<span data-ttu-id="f681f-124">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="f681f-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="f681f-125">Debug</span><span class="sxs-lookup"><span data-stu-id="f681f-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
