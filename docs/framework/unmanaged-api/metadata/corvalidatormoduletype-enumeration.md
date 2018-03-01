---
title: Enumerazione CorValidatorModuleType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3367f6928b5d7378b2686185ee3e03d0279cc11d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="06c14-102">Enumerazione CorValidatorModuleType</span><span class="sxs-lookup"><span data-stu-id="06c14-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="06c14-103">Specifica il tipo di un modulo.</span><span class="sxs-lookup"><span data-stu-id="06c14-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06c14-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06c14-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a><span data-ttu-id="06c14-105">Membri</span><span class="sxs-lookup"><span data-stu-id="06c14-105">Members</span></span>  
  
|<span data-ttu-id="06c14-106">Membro</span><span class="sxs-lookup"><span data-stu-id="06c14-106">Member</span></span>|<span data-ttu-id="06c14-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06c14-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="06c14-108">Il modulo è un tipo non valido.</span><span class="sxs-lookup"><span data-stu-id="06c14-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="06c14-109">Il valore minimo di `CorValidatorModuleType` enum.</span><span class="sxs-lookup"><span data-stu-id="06c14-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="06c14-110">Il modulo è un file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="06c14-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="06c14-111">Il modulo è un file con estensione obj.</span><span class="sxs-lookup"><span data-stu-id="06c14-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="06c14-112">Il modulo è una sessione di modifica e continuazione del debugger.</span><span class="sxs-lookup"><span data-stu-id="06c14-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="06c14-113">Il modulo è quello che è stata compilata in modo incrementale.</span><span class="sxs-lookup"><span data-stu-id="06c14-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="06c14-114">Il valore massimo di `CorValidatorModuleType` enum.</span><span class="sxs-lookup"><span data-stu-id="06c14-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06c14-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06c14-115">Requirements</span></span>  
 <span data-ttu-id="06c14-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06c14-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06c14-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="06c14-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06c14-118">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="06c14-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06c14-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06c14-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06c14-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06c14-120">See Also</span></span>  
 [<span data-ttu-id="06c14-121">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="06c14-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
