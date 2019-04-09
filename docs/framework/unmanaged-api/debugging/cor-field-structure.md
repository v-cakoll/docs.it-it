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
ms.openlocfilehash: 691041632312bf8ac7c82a11724dcd725e14a420
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231058"
---
# <a name="corfield-structure"></a><span data-ttu-id="80213-102">Struttura COR_FIELD</span><span class="sxs-lookup"><span data-stu-id="80213-102">COR_FIELD Structure</span></span>
<span data-ttu-id="80213-103">Fornisce informazioni su un campo in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="80213-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80213-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80213-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="80213-105">Membri</span><span class="sxs-lookup"><span data-stu-id="80213-105">Members</span></span>  
  
|<span data-ttu-id="80213-106">Member</span><span class="sxs-lookup"><span data-stu-id="80213-106">Member</span></span>|<span data-ttu-id="80213-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80213-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="80213-108">Un `mdFieldDef` token che può essere usato per ottenere informazioni sui campi.</span><span class="sxs-lookup"><span data-stu-id="80213-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="80213-109">Offset, in byte, per i dati del campo nell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="80213-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="80213-110">Oggetto [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) valore che identifica il tipo di questo campo.</span><span class="sxs-lookup"><span data-stu-id="80213-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="80213-111">Valore di enumerazione CorElementType che indica il tipo del campo.</span><span class="sxs-lookup"><span data-stu-id="80213-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80213-112">Note</span><span class="sxs-lookup"><span data-stu-id="80213-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80213-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80213-113">Requirements</span></span>  
 <span data-ttu-id="80213-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80213-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80213-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80213-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80213-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80213-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="80213-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="80213-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="80213-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80213-118">See also</span></span>

- [<span data-ttu-id="80213-119">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="80213-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="80213-120">Debug</span><span class="sxs-lookup"><span data-stu-id="80213-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
