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
ms.openlocfilehash: 7efb2c3e8033b8bd8fa736a29b2ab9b3bedebeaa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609503"
---
# <a name="cortypelayout-structure"></a><span data-ttu-id="dcc86-102">Struttura COR_TYPE_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="dcc86-102">COR_TYPE_LAYOUT Structure</span></span>
<span data-ttu-id="dcc86-103">Fornisce informazioni sul layout di un oggetto in memoria.</span><span class="sxs-lookup"><span data-stu-id="dcc86-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcc86-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dcc86-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="dcc86-105">Membri</span><span class="sxs-lookup"><span data-stu-id="dcc86-105">Members</span></span>  
  
|<span data-ttu-id="dcc86-106">Member</span><span class="sxs-lookup"><span data-stu-id="dcc86-106">Member</span></span>|<span data-ttu-id="dcc86-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dcc86-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="dcc86-108">L'identificatore del tipo padre per questo tipo.</span><span class="sxs-lookup"><span data-stu-id="dcc86-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="dcc86-109">Questo sarà l'id di tipo NULL (token1 = 0, token2 = 0) se l'id del tipo corrisponde a <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dcc86-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="dcc86-110">Le dimensioni di base di un oggetto di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="dcc86-110">The base size of an object of this type.</span></span> <span data-ttu-id="dcc86-111">Questa è la dimensione totale per gli oggetti con dimensione non variabile.</span><span class="sxs-lookup"><span data-stu-id="dcc86-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="dcc86-112">Il numero di campi inclusi negli oggetti di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="dcc86-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="dcc86-113">Se questo tipo è di tipo boxed, inizio offset di campi di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="dcc86-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="dcc86-114">Questo campo è valido solo per i tipi di valore, ad esempio le primitive e strutture.</span><span class="sxs-lookup"><span data-stu-id="dcc86-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="dcc86-115">CorElementType a cui appartiene questo tipo.</span><span class="sxs-lookup"><span data-stu-id="dcc86-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcc86-116">Note</span><span class="sxs-lookup"><span data-stu-id="dcc86-116">Remarks</span></span>  
 <span data-ttu-id="dcc86-117">Se `numFields` è maggiore di zero, è possibile chiamare il [ICorDebugProcess5::GetTypeFields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) metodo per ottenere informazioni sui campi di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="dcc86-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="dcc86-118">Se `type` viene `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, o `ELEMENT_TYPE_SZARRAY`, la dimensione degli oggetti di questo tipo è variabile ed è possibile passare il [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) struttura per il [ICorDebugProcess5::GetArrayLayout ](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="dcc86-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcc86-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dcc86-119">Requirements</span></span>  
 <span data-ttu-id="dcc86-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcc86-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcc86-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcc86-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcc86-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcc86-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcc86-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcc86-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcc86-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcc86-124">See also</span></span>

- [<span data-ttu-id="dcc86-125">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="dcc86-125">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="dcc86-126">Debug</span><span class="sxs-lookup"><span data-stu-id="dcc86-126">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
