---
title: Struttura COR_FIELD
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_FIELD
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_FIELD
helpviewer_keywords: COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 09a96a22a653688540bcc2ea3a03d86e242c10f5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corfield-structure"></a><span data-ttu-id="f300c-102">Struttura COR_FIELD</span><span class="sxs-lookup"><span data-stu-id="f300c-102">COR_FIELD Structure</span></span>
<span data-ttu-id="f300c-103">Fornisce informazioni su un campo in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="f300c-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f300c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f300c-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="f300c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f300c-105">Members</span></span>  
  
|<span data-ttu-id="f300c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f300c-106">Member</span></span>|<span data-ttu-id="f300c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f300c-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="f300c-108">Un `mdFieldDef` token che può essere utilizzato per ottenere informazioni sui campi.</span><span class="sxs-lookup"><span data-stu-id="f300c-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="f300c-109">L'offset in byte, per i dati del campo nell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f300c-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="f300c-110">Oggetto [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) valore che identifica il tipo di questo campo.</span><span class="sxs-lookup"><span data-stu-id="f300c-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="f300c-111">Valore di enumerazione CorElementType che indica il tipo del campo.</span><span class="sxs-lookup"><span data-stu-id="f300c-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f300c-112">Note</span><span class="sxs-lookup"><span data-stu-id="f300c-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f300c-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f300c-113">Requirements</span></span>  
 <span data-ttu-id="f300c-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f300c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f300c-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f300c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f300c-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f300c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f300c-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f300c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f300c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f300c-118">See Also</span></span>  
 [<span data-ttu-id="f300c-119">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="f300c-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="f300c-120">Debug</span><span class="sxs-lookup"><span data-stu-id="f300c-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
