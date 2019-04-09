---
title: Enumerazione CorArgType
ms.date: 03/30/2017
api_name:
- CorArgType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorArgType
helpviewer_keywords:
- CorArgType enumeration [.NET Framework metadata]
ms.assetid: 3c1cb268-57a0-4664-91c7-f6908ff29e32
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: af9ca932a4c4a12a2c89571f40162a4ecbd5c33d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144495"
---
# <a name="corargtype-enumeration"></a><span data-ttu-id="94eb4-102">Enumerazione CorArgType</span><span class="sxs-lookup"><span data-stu-id="94eb4-102">CorArgType Enumeration</span></span>
<span data-ttu-id="94eb4-103">Contiene valori che descrivono il tipo nativo di un handle di runtime.</span><span class="sxs-lookup"><span data-stu-id="94eb4-103">Contains values that describe the native type of a runtime handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94eb4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94eb4-104">Syntax</span></span>  
  
```  
typedef enum CorArgType {  
  
    IMAGE_CEE_CS_END        = 0x0,  
    IMAGE_CEE_CS_VOID       = 0x1,  
    IMAGE_CEE_CS_I4         = 0x2,  
    IMAGE_CEE_CS_I8         = 0x3,  
    IMAGE_CEE_CS_R4         = 0x4,  
    IMAGE_CEE_CS_R8         = 0x5,  
    IMAGE_CEE_CS_PTR        = 0x6,  
    IMAGE_CEE_CS_OBJECT     = 0x7,  
    IMAGE_CEE_CS_STRUCT4    = 0x8,  
    IMAGE_CEE_CS_STRUCT32   = 0x9,  
    IMAGE_CEE_CS_BYVALUE    = 0xA  
  
} CorArgType;  
```  
  
## <a name="requirements"></a><span data-ttu-id="94eb4-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94eb4-105">Requirements</span></span>  
 <span data-ttu-id="94eb4-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94eb4-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94eb4-107">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="94eb4-107">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="94eb4-108">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="94eb4-108">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="94eb4-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94eb4-109">See also</span></span>

- [<span data-ttu-id="94eb4-110">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="94eb4-110">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
