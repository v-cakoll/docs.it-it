---
title: Enumerazione CorLocalRefPreservation
ms.date: 03/30/2017
api_name:
- CorLocalRefPreservation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLocalRefPreservation
helpviewer_keywords:
- CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ee808ba403a513b897134420b45ebe8cd3537571
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442246"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="c5423-102">Enumerazione CorLocalRefPreservation</span><span class="sxs-lookup"><span data-stu-id="c5423-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="c5423-103">Contiene valori di flag per il trattamento dei riferimenti locali.</span><span class="sxs-lookup"><span data-stu-id="c5423-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5423-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5423-104">Syntax</span></span>  
  
```  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="c5423-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c5423-105">Members</span></span>  
  
|<span data-ttu-id="c5423-106">Membro</span><span class="sxs-lookup"><span data-stu-id="c5423-106">Member</span></span>|<span data-ttu-id="c5423-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5423-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="c5423-108">Non mantenere i riferimenti locali.</span><span class="sxs-lookup"><span data-stu-id="c5423-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="c5423-109">Mantenere i riferimenti al tipo locale.</span><span class="sxs-lookup"><span data-stu-id="c5423-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="c5423-110">Mantenere i riferimenti membro locale.</span><span class="sxs-lookup"><span data-stu-id="c5423-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c5423-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c5423-111">Requirements</span></span>  
 <span data-ttu-id="c5423-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5423-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5423-113">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="c5423-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c5423-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5423-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5423-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5423-115">See Also</span></span>  
 [<span data-ttu-id="c5423-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="c5423-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
