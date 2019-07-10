---
title: Enumerazione CorParamAttr
ms.date: 03/30/2017
api_name:
- CorParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorParamAttr
helpviewer_keywords:
- CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bfa8f1b5df76c7fdfe2f25b637b157bfa4424f7a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781659"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="c0014-102">Enumerazione CorParamAttr</span><span class="sxs-lookup"><span data-stu-id="c0014-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="c0014-103">Contiene valori che descrivono i metadati di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="c0014-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0014-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0014-104">Syntax</span></span>  
  
```cpp  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="c0014-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c0014-105">Members</span></span>  
  
|<span data-ttu-id="c0014-106">Member</span><span class="sxs-lookup"><span data-stu-id="c0014-106">Member</span></span>|<span data-ttu-id="c0014-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0014-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="c0014-108">Specifica che il parametro viene passato nella chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="c0014-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="c0014-109">Specifica che il parametro viene passato dal metodo restituito.</span><span class="sxs-lookup"><span data-stu-id="c0014-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="c0014-110">Specifica che il parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c0014-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="c0014-111">Riservato per uso interno da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="c0014-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="c0014-112">Specifica che il parametro ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="c0014-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="c0014-113">Specifica che il parametro contiene le informazioni di marshalling.</span><span class="sxs-lookup"><span data-stu-id="c0014-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="c0014-114">Non usato.</span><span class="sxs-lookup"><span data-stu-id="c0014-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0014-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0014-115">Requirements</span></span>  
 <span data-ttu-id="c0014-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0014-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0014-117">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="c0014-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c0014-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0014-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0014-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0014-119">See also</span></span>

- [<span data-ttu-id="c0014-120">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="c0014-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
