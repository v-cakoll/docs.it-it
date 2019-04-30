---
title: Enumerazione CorValidatorModuleType
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 14eee096c25967d321e4693b260501827d944a80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045175"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="f6053-102">Enumerazione CorValidatorModuleType</span><span class="sxs-lookup"><span data-stu-id="f6053-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="f6053-103">Specifica il tipo di un modulo.</span><span class="sxs-lookup"><span data-stu-id="f6053-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6053-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6053-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="f6053-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f6053-105">Members</span></span>  
  
|<span data-ttu-id="f6053-106">Member</span><span class="sxs-lookup"><span data-stu-id="f6053-106">Member</span></span>|<span data-ttu-id="f6053-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6053-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="f6053-108">Il modulo è un tipo non valido.</span><span class="sxs-lookup"><span data-stu-id="f6053-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="f6053-109">Il valore minimo del `CorValidatorModuleType` enum.</span><span class="sxs-lookup"><span data-stu-id="f6053-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="f6053-110">Il modulo è un file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="f6053-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="f6053-111">Il modulo è un file con estensione obj.</span><span class="sxs-lookup"><span data-stu-id="f6053-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="f6053-112">Il modulo è una sessione di modifica e continuazione del debugger.</span><span class="sxs-lookup"><span data-stu-id="f6053-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="f6053-113">Il modulo è quello che è stata compilata in modo incrementale.</span><span class="sxs-lookup"><span data-stu-id="f6053-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="f6053-114">Il valore massimo del `CorValidatorModuleType` enum.</span><span class="sxs-lookup"><span data-stu-id="f6053-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f6053-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f6053-115">Requirements</span></span>  
 <span data-ttu-id="f6053-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6053-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6053-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f6053-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f6053-118">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f6053-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6053-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6053-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6053-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6053-120">See also</span></span>

- [<span data-ttu-id="f6053-121">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="f6053-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
