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
ms.openlocfilehash: 038e2ec20e5fd01edf9835080e0f7a15ec862fd9
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008937"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="9967d-102">Enumerazione CorValidatorModuleType</span><span class="sxs-lookup"><span data-stu-id="9967d-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="9967d-103">Specifica il tipo di un modulo.</span><span class="sxs-lookup"><span data-stu-id="9967d-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9967d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9967d-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="9967d-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9967d-105">Members</span></span>  
  
|<span data-ttu-id="9967d-106">Membro</span><span class="sxs-lookup"><span data-stu-id="9967d-106">Member</span></span>|<span data-ttu-id="9967d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9967d-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="9967d-108">Il modulo non è un tipo valido.</span><span class="sxs-lookup"><span data-stu-id="9967d-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="9967d-109">Valore minimo dell' `CorValidatorModuleType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9967d-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="9967d-110">Il modulo è un file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="9967d-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="9967d-111">Il modulo è un file con estensione obj.</span><span class="sxs-lookup"><span data-stu-id="9967d-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="9967d-112">Il modulo è una sessione del debugger di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="9967d-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="9967d-113">Il modulo è un modulo che è stato compilato in modo incrementale.</span><span class="sxs-lookup"><span data-stu-id="9967d-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="9967d-114">Valore massimo dell' `CorValidatorModuleType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9967d-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9967d-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9967d-115">Requirements</span></span>  
 <span data-ttu-id="9967d-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9967d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9967d-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9967d-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9967d-118">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9967d-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9967d-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9967d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9967d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9967d-120">See also</span></span>

- [<span data-ttu-id="9967d-121">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="9967d-121">Metadata Enumerations</span></span>](metadata-enumerations.md)
