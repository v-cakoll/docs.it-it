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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092058"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="80db8-102">Enumerazione CorParamAttr</span><span class="sxs-lookup"><span data-stu-id="80db8-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="80db8-103">Contiene valori che descrivono i metadati di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="80db8-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80db8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80db8-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="80db8-105">Membri</span><span class="sxs-lookup"><span data-stu-id="80db8-105">Members</span></span>  
  
|<span data-ttu-id="80db8-106">Member</span><span class="sxs-lookup"><span data-stu-id="80db8-106">Member</span></span>|<span data-ttu-id="80db8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80db8-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="80db8-108">Specifica che il parametro viene passato nella chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="80db8-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="80db8-109">Specifica che il parametro viene passato dal metodo restituito.</span><span class="sxs-lookup"><span data-stu-id="80db8-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="80db8-110">Specifica che il parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="80db8-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="80db8-111">Riservato per uso interno da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="80db8-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="80db8-112">Specifica che il parametro ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="80db8-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="80db8-113">Specifica che il parametro contiene le informazioni di marshalling.</span><span class="sxs-lookup"><span data-stu-id="80db8-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="80db8-114">Non usato.</span><span class="sxs-lookup"><span data-stu-id="80db8-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="80db8-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80db8-115">Requirements</span></span>  
 <span data-ttu-id="80db8-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80db8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80db8-117">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="80db8-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="80db8-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80db8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80db8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80db8-119">See also</span></span>

- [<span data-ttu-id="80db8-120">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="80db8-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
