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
ms.openlocfilehash: 97f62b082db11a5f0bb930e33cb47acef76e7a04
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092058"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="d3015-102">Enumerazione CorParamAttr</span><span class="sxs-lookup"><span data-stu-id="d3015-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="d3015-103">Contiene valori che descrivono i metadati di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="d3015-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3015-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3015-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="d3015-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d3015-105">Members</span></span>  
  
|<span data-ttu-id="d3015-106">Member</span><span class="sxs-lookup"><span data-stu-id="d3015-106">Member</span></span>|<span data-ttu-id="d3015-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3015-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="d3015-108">Specifica che il parametro viene passato nella chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="d3015-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="d3015-109">Specifica che il parametro viene passato dal metodo restituito.</span><span class="sxs-lookup"><span data-stu-id="d3015-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="d3015-110">Specifica che il parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d3015-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="d3015-111">Riservato per uso interno da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="d3015-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="d3015-112">Specifica che il parametro ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="d3015-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="d3015-113">Specifica che il parametro contiene le informazioni di marshalling.</span><span class="sxs-lookup"><span data-stu-id="d3015-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="d3015-114">Non usato.</span><span class="sxs-lookup"><span data-stu-id="d3015-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3015-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3015-115">Requirements</span></span>  
 <span data-ttu-id="d3015-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3015-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3015-117">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="d3015-117">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="d3015-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d3015-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d3015-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3015-119">See also</span></span>

- [<span data-ttu-id="d3015-120">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="d3015-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
