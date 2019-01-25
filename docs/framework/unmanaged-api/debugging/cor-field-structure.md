---
title: Struttura COR_FIELD
ms.date: 03/30/2017
api_name:
- COR_FIELD
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_FIELD
helpviewer_keywords:
- COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d570f9392bbd66f0d9031c776b139ee3b30541b1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698219"
---
# <a name="corfield-structure"></a><span data-ttu-id="a7d0c-102">Struttura COR_FIELD</span><span class="sxs-lookup"><span data-stu-id="a7d0c-102">COR_FIELD Structure</span></span>
<span data-ttu-id="a7d0c-103">Fornisce informazioni su un campo in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="a7d0c-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7d0c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7d0c-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="a7d0c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a7d0c-105">Members</span></span>  
  
|<span data-ttu-id="a7d0c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="a7d0c-106">Member</span></span>|<span data-ttu-id="a7d0c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a7d0c-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="a7d0c-108">Un `mdFieldDef` token che può essere usato per ottenere informazioni sui campi.</span><span class="sxs-lookup"><span data-stu-id="a7d0c-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="a7d0c-109">Offset, in byte, per i dati del campo nell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="a7d0c-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="a7d0c-110">Oggetto [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) valore che identifica il tipo di questo campo.</span><span class="sxs-lookup"><span data-stu-id="a7d0c-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="a7d0c-111">Valore di enumerazione CorElementType che indica il tipo del campo.</span><span class="sxs-lookup"><span data-stu-id="a7d0c-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7d0c-112">Note</span><span class="sxs-lookup"><span data-stu-id="a7d0c-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7d0c-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7d0c-113">Requirements</span></span>  
 <span data-ttu-id="a7d0c-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7d0c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7d0c-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7d0c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7d0c-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7d0c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7d0c-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7d0c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7d0c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7d0c-118">See also</span></span>
- [<span data-ttu-id="a7d0c-119">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="a7d0c-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="a7d0c-120">Debug</span><span class="sxs-lookup"><span data-stu-id="a7d0c-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
