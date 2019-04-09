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
ms.openlocfilehash: 845994b96445d8ec2a0e37affc5164b432894a91
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102193"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="276ed-102">Enumerazione CorLocalRefPreservation</span><span class="sxs-lookup"><span data-stu-id="276ed-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="276ed-103">Contiene valori di flag per il trattamento dei riferimenti locali.</span><span class="sxs-lookup"><span data-stu-id="276ed-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="276ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="276ed-104">Syntax</span></span>  
  
```  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="276ed-105">Membri</span><span class="sxs-lookup"><span data-stu-id="276ed-105">Members</span></span>  
  
|<span data-ttu-id="276ed-106">Member</span><span class="sxs-lookup"><span data-stu-id="276ed-106">Member</span></span>|<span data-ttu-id="276ed-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="276ed-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="276ed-108">Non Preserve riferimenti locali.</span><span class="sxs-lookup"><span data-stu-id="276ed-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="276ed-109">Mantenere i riferimenti ai tipi locali.</span><span class="sxs-lookup"><span data-stu-id="276ed-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="276ed-110">Mantenere i riferimenti membro locale.</span><span class="sxs-lookup"><span data-stu-id="276ed-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="276ed-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="276ed-111">Requirements</span></span>  
 <span data-ttu-id="276ed-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="276ed-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="276ed-113">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="276ed-113">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="276ed-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="276ed-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="276ed-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="276ed-115">See also</span></span>

- [<span data-ttu-id="276ed-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="276ed-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
