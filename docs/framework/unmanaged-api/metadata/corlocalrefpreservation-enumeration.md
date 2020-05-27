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
ms.openlocfilehash: 42cb4e76bb77aebcee3b28035635a877513cdc04
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008989"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="af24b-102">Enumerazione CorLocalRefPreservation</span><span class="sxs-lookup"><span data-stu-id="af24b-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="af24b-103">Contiene valori di flag per il trattamento dei riferimenti locali.</span><span class="sxs-lookup"><span data-stu-id="af24b-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af24b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af24b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="af24b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="af24b-105">Members</span></span>  
  
|<span data-ttu-id="af24b-106">Membro</span><span class="sxs-lookup"><span data-stu-id="af24b-106">Member</span></span>|<span data-ttu-id="af24b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af24b-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="af24b-108">Non mantenere riferimenti locali.</span><span class="sxs-lookup"><span data-stu-id="af24b-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="af24b-109">Mantieni i riferimenti ai tipi locali.</span><span class="sxs-lookup"><span data-stu-id="af24b-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="af24b-110">Conserva i riferimenti ai membri locali.</span><span class="sxs-lookup"><span data-stu-id="af24b-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af24b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="af24b-111">Requirements</span></span>  
 <span data-ttu-id="af24b-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af24b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af24b-113">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="af24b-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="af24b-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af24b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af24b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af24b-115">See also</span></span>

- [<span data-ttu-id="af24b-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="af24b-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
