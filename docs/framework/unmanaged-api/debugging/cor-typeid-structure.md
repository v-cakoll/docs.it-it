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
ms.openlocfilehash: 5d76fa4b2352da18b5ef0e547ebc4e2e99d980b8
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71273990"
---
# <a name="cor_typeid-structure"></a><span data-ttu-id="f5fbb-102">Struttura COR_TYPEID</span><span class="sxs-lookup"><span data-stu-id="f5fbb-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="f5fbb-103">Contiene un identificatore di tipo.</span><span class="sxs-lookup"><span data-stu-id="f5fbb-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5fbb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5fbb-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="f5fbb-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f5fbb-105">Members</span></span>  
  
|<span data-ttu-id="f5fbb-106">Member</span><span class="sxs-lookup"><span data-stu-id="f5fbb-106">Member</span></span>|<span data-ttu-id="f5fbb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5fbb-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="f5fbb-108">Primo token.</span><span class="sxs-lookup"><span data-stu-id="f5fbb-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="f5fbb-109">Secondo token.</span><span class="sxs-lookup"><span data-stu-id="f5fbb-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5fbb-110">Note</span><span class="sxs-lookup"><span data-stu-id="f5fbb-110">Remarks</span></span>  
 <span data-ttu-id="f5fbb-111">La `COR_TYPEID` struttura viene restituita da una serie di metodi di debug che forniscono informazioni sugli oggetti che devono essere sottoposti a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f5fbb-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="f5fbb-112">Può quindi essere passato come argomento ad altri metodi di debug che forniscono informazioni aggiuntive su tale elemento.</span><span class="sxs-lookup"><span data-stu-id="f5fbb-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="f5fbb-113">Tramite l'enumerazione di un oggetto [ICorDebugHeapEnum](icordebugheapenum-interface.md) , ad esempio, è possibile recuperare singoli oggetti [COR_HEAPOBJECT](cor-heapobject-structure.md) che rappresentano singoli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="f5fbb-113">For example, by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="f5fbb-114">È quindi possibile passare il `COR_TYPEID` valore `COR_HEAPOBJECT.type` dal campo al metodo [ICorDebugProcess5:: GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) per recuperare un oggetto ICorDebugType che fornisce informazioni sul tipo relative all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f5fbb-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="f5fbb-115">Un `COR_TYPEID` oggetto deve essere opaco.</span><span class="sxs-lookup"><span data-stu-id="f5fbb-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="f5fbb-116">Non è possibile accedere o modificare i singoli campi.</span><span class="sxs-lookup"><span data-stu-id="f5fbb-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="f5fbb-117">Il suo unico utilizzo è come un identificatore fornito come `out` parametro in una chiamata al metodo e che, a sua volta, può essere passato ad altri metodi per fornire informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="f5fbb-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5fbb-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f5fbb-118">Requirements</span></span>  
 <span data-ttu-id="f5fbb-119">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5fbb-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5fbb-120">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f5fbb-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5fbb-121">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5fbb-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5fbb-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5fbb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5fbb-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5fbb-123">See also</span></span>

- [<span data-ttu-id="f5fbb-124">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="f5fbb-124">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="f5fbb-125">Debug</span><span class="sxs-lookup"><span data-stu-id="f5fbb-125">Debugging</span></span>](index.md)
