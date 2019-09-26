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
ms.openlocfilehash: f857f773f02da25fe6650000be777b8290f5af91
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274065"
---
# <a name="cor_field-structure"></a><span data-ttu-id="1c0e3-102">Struttura COR_FIELD</span><span class="sxs-lookup"><span data-stu-id="1c0e3-102">COR_FIELD Structure</span></span>
<span data-ttu-id="1c0e3-103">Fornisce informazioni su un campo in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c0e3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c0e3-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="1c0e3-105">Membri</span><span class="sxs-lookup"><span data-stu-id="1c0e3-105">Members</span></span>  
  
|<span data-ttu-id="1c0e3-106">Member</span><span class="sxs-lookup"><span data-stu-id="1c0e3-106">Member</span></span>|<span data-ttu-id="1c0e3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c0e3-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="1c0e3-108">`mdFieldDef` Token che può essere usato per ottenere informazioni sui campi.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="1c0e3-109">Offset, in byte, per i dati dei campi nell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="1c0e3-110">Valore [COR_TYPEID](cor-typeid-structure.md) che identifica il tipo di questo campo.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-110">A [COR_TYPEID](cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="1c0e3-111">Valore di enumerazione CorElementType che indica il tipo del campo.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c0e3-112">Note</span><span class="sxs-lookup"><span data-stu-id="1c0e3-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c0e3-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c0e3-113">Requirements</span></span>  
 <span data-ttu-id="1c0e3-114">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c0e3-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c0e3-115">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="1c0e3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c0e3-116">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c0e3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c0e3-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c0e3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c0e3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c0e3-118">See also</span></span>

- [<span data-ttu-id="1c0e3-119">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="1c0e3-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="1c0e3-120">Debug</span><span class="sxs-lookup"><span data-stu-id="1c0e3-120">Debugging</span></span>](index.md)
