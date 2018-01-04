---
title: Enumerazione CorLocalRefPreservation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorLocalRefPreservation
api_location: mscoree.dll
api_type: COM
f1_keywords: CorLocalRefPreservation
helpviewer_keywords: CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c35bbfef62f65a9a401d00f9ae56e2f4c00bb0b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="cc21b-102">Enumerazione CorLocalRefPreservation</span><span class="sxs-lookup"><span data-stu-id="cc21b-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="cc21b-103">Contiene valori di flag per il trattamento dei riferimenti locali.</span><span class="sxs-lookup"><span data-stu-id="cc21b-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc21b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc21b-104">Syntax</span></span>  
  
```  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="cc21b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="cc21b-105">Members</span></span>  
  
|<span data-ttu-id="cc21b-106">Membro</span><span class="sxs-lookup"><span data-stu-id="cc21b-106">Member</span></span>|<span data-ttu-id="cc21b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc21b-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="cc21b-108">Non mantenere i riferimenti locali.</span><span class="sxs-lookup"><span data-stu-id="cc21b-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="cc21b-109">Mantenere i riferimenti al tipo locale.</span><span class="sxs-lookup"><span data-stu-id="cc21b-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="cc21b-110">Mantenere i riferimenti membro locale.</span><span class="sxs-lookup"><span data-stu-id="cc21b-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc21b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cc21b-111">Requirements</span></span>  
 <span data-ttu-id="cc21b-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc21b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc21b-113">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="cc21b-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="cc21b-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc21b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc21b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc21b-115">See Also</span></span>  
 [<span data-ttu-id="cc21b-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="cc21b-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
