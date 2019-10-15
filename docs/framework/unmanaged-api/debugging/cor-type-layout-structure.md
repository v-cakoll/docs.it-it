---
title: Struttura COR_TYPE_LAYOUT
ms.date: 03/30/2017
api_name:
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bd274b1eb14532629580e777288317186544912
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274160"
---
# <a name="cor_type_layout-structure"></a><span data-ttu-id="2aa3e-102">Struttura COR_TYPE_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="2aa3e-102">COR_TYPE_LAYOUT Structure</span></span>
<span data-ttu-id="2aa3e-103">Fornisce informazioni sul layout di un oggetto in memoria.</span><span class="sxs-lookup"><span data-stu-id="2aa3e-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aa3e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2aa3e-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="2aa3e-105">Membri</span><span class="sxs-lookup"><span data-stu-id="2aa3e-105">Members</span></span>  
  
|<span data-ttu-id="2aa3e-106">Member</span><span class="sxs-lookup"><span data-stu-id="2aa3e-106">Member</span></span>|<span data-ttu-id="2aa3e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2aa3e-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="2aa3e-108">Identificatore del tipo padre a questo tipo.</span><span class="sxs-lookup"><span data-stu-id="2aa3e-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="2aa3e-109">Si tratta dell'ID di tipo NULL (token1 = 0, token2 = 0) se l'ID del tipo corrisponde <xref:System.Object?displayProperty=nameWithType>a.</span><span class="sxs-lookup"><span data-stu-id="2aa3e-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="2aa3e-110">Dimensioni di base di un oggetto di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="2aa3e-110">The base size of an object of this type.</span></span> <span data-ttu-id="2aa3e-111">Dimensioni totali per gli oggetti di dimensioni non variabili.</span><span class="sxs-lookup"><span data-stu-id="2aa3e-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="2aa3e-112">Numero di campi inclusi negli oggetti di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="2aa3e-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="2aa3e-113">Se questo tipo è boxed, l'offset iniziale dei campi di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="2aa3e-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="2aa3e-114">Questo campo è valido solo per i tipi di valore come le primitive e le strutture.</span><span class="sxs-lookup"><span data-stu-id="2aa3e-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="2aa3e-115">CorElementType a cui appartiene questo tipo.</span><span class="sxs-lookup"><span data-stu-id="2aa3e-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2aa3e-116">Note</span><span class="sxs-lookup"><span data-stu-id="2aa3e-116">Remarks</span></span>  
 <span data-ttu-id="2aa3e-117">Se `numFields` è maggiore di zero, è possibile chiamare il metodo [ICorDebugProcess5:: GetTypeFields](icordebugprocess5-gettypefields-method.md) per ottenere informazioni sui campi di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="2aa3e-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="2aa3e-118">Se `type` è `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY` o `ELEMENT_TYPE_SZARRAY`, le dimensioni degli oggetti di questo tipo sono variabili ed è possibile passare la struttura [COR_TYPEID](cor-typeid-structure.md) al metodo [ICorDebugProcess5::GetArrayLayout](icordebugprocess5-getarraylayout-method.md).</span><span class="sxs-lookup"><span data-stu-id="2aa3e-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aa3e-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2aa3e-119">Requirements</span></span>  
 <span data-ttu-id="2aa3e-120">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2aa3e-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aa3e-121">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="2aa3e-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2aa3e-122">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2aa3e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2aa3e-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aa3e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa3e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2aa3e-124">See also</span></span>

- [<span data-ttu-id="2aa3e-125">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="2aa3e-125">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="2aa3e-126">Debug</span><span class="sxs-lookup"><span data-stu-id="2aa3e-126">Debugging</span></span>](index.md)
