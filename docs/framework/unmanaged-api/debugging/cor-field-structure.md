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
ms.openlocfilehash: 78e34d9d33d34047e3ebd2effb4894bc7b709585
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132351"
---
# <a name="cor_field-structure"></a><span data-ttu-id="5645c-102">Struttura COR_FIELD</span><span class="sxs-lookup"><span data-stu-id="5645c-102">COR_FIELD Structure</span></span>
<span data-ttu-id="5645c-103">Fornisce informazioni su un campo in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="5645c-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5645c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5645c-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="5645c-105">Members</span><span class="sxs-lookup"><span data-stu-id="5645c-105">Members</span></span>  
  
|<span data-ttu-id="5645c-106">Member</span><span class="sxs-lookup"><span data-stu-id="5645c-106">Member</span></span>|<span data-ttu-id="5645c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5645c-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="5645c-108">Token `mdFieldDef` che può essere utilizzato per ottenere informazioni sui campi.</span><span class="sxs-lookup"><span data-stu-id="5645c-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="5645c-109">Offset, in byte, per i dati dei campi nell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="5645c-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="5645c-110">Valore [COR_TYPEID](cor-typeid-structure.md) che identifica il tipo di questo campo.</span><span class="sxs-lookup"><span data-stu-id="5645c-110">A [COR_TYPEID](cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="5645c-111">Valore di enumerazione CorElementType che indica il tipo del campo.</span><span class="sxs-lookup"><span data-stu-id="5645c-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5645c-112">Note</span><span class="sxs-lookup"><span data-stu-id="5645c-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5645c-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5645c-113">Requirements</span></span>  
 <span data-ttu-id="5645c-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5645c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5645c-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5645c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5645c-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5645c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5645c-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5645c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5645c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5645c-118">See also</span></span>

- [<span data-ttu-id="5645c-119">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="5645c-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="5645c-120">Debug</span><span class="sxs-lookup"><span data-stu-id="5645c-120">Debugging</span></span>](index.md)
