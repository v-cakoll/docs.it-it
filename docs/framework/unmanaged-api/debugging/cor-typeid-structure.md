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
ms.openlocfilehash: 4f6dbe8c17bd6a91078b87a87c1055fbf4977a88
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132304"
---
# <a name="cor_typeid-structure"></a><span data-ttu-id="f5121-102">Struttura COR_TYPEID</span><span class="sxs-lookup"><span data-stu-id="f5121-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="f5121-103">Contiene un identificatore di tipo.</span><span class="sxs-lookup"><span data-stu-id="f5121-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5121-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5121-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="f5121-105">Members</span><span class="sxs-lookup"><span data-stu-id="f5121-105">Members</span></span>  
  
|<span data-ttu-id="f5121-106">Member</span><span class="sxs-lookup"><span data-stu-id="f5121-106">Member</span></span>|<span data-ttu-id="f5121-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5121-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="f5121-108">Primo token.</span><span class="sxs-lookup"><span data-stu-id="f5121-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="f5121-109">Secondo token.</span><span class="sxs-lookup"><span data-stu-id="f5121-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5121-110">Note</span><span class="sxs-lookup"><span data-stu-id="f5121-110">Remarks</span></span>  
 <span data-ttu-id="f5121-111">La struttura `COR_TYPEID` viene restituita da una serie di metodi di debug che forniscono informazioni sugli oggetti da sottoposta a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f5121-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="f5121-112">Può quindi essere passato come argomento ad altri metodi di debug che forniscono informazioni aggiuntive su tale elemento.</span><span class="sxs-lookup"><span data-stu-id="f5121-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="f5121-113">Tramite l'enumerazione di un oggetto [ICorDebugHeapEnum](icordebugheapenum-interface.md) , ad esempio, è possibile recuperare singoli oggetti [COR_HEAPOBJECT](cor-heapobject-structure.md) che rappresentano singoli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="f5121-113">For example, by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="f5121-114">È quindi possibile passare il valore `COR_TYPEID` dal campo `COR_HEAPOBJECT.type` al metodo [ICorDebugProcess5:: GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) per recuperare un oggetto ICorDebugType che fornisce informazioni sul tipo relative all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f5121-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="f5121-115">Un oggetto `COR_TYPEID` è progettato per essere opaco.</span><span class="sxs-lookup"><span data-stu-id="f5121-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="f5121-116">Non è possibile accedere o modificare i singoli campi.</span><span class="sxs-lookup"><span data-stu-id="f5121-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="f5121-117">Il suo unico utilizzo è come un identificatore fornito come parametro `out` in una chiamata al metodo e che, a sua volta, può essere passato ad altri metodi per fornire informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="f5121-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5121-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f5121-118">Requirements</span></span>  
 <span data-ttu-id="f5121-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5121-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5121-120">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5121-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5121-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5121-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5121-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5121-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5121-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5121-123">See also</span></span>

- [<span data-ttu-id="f5121-124">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="f5121-124">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="f5121-125">Debug</span><span class="sxs-lookup"><span data-stu-id="f5121-125">Debugging</span></span>](index.md)
