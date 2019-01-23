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
ms.openlocfilehash: 7d07c6de47038d5c52d76ad8ca8e0a5684551d59
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491467"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="110a3-102">Enumerazione CorParamAttr</span><span class="sxs-lookup"><span data-stu-id="110a3-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="110a3-103">Contiene valori che descrivono i metadati di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="110a3-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="110a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="110a3-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="110a3-105">Membri</span><span class="sxs-lookup"><span data-stu-id="110a3-105">Members</span></span>  
  
|<span data-ttu-id="110a3-106">Membro</span><span class="sxs-lookup"><span data-stu-id="110a3-106">Member</span></span>|<span data-ttu-id="110a3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="110a3-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="110a3-108">Specifica che il parametro viene passato nella chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="110a3-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="110a3-109">Specifica che il parametro viene passato dal metodo restituito.</span><span class="sxs-lookup"><span data-stu-id="110a3-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="110a3-110">Specifica che il parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="110a3-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="110a3-111">Riservato per uso interno da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="110a3-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="110a3-112">Specifica che il parametro ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="110a3-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="110a3-113">Specifica che il parametro contiene le informazioni di marshalling.</span><span class="sxs-lookup"><span data-stu-id="110a3-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="110a3-114">Non usato.</span><span class="sxs-lookup"><span data-stu-id="110a3-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="110a3-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="110a3-115">Requirements</span></span>  
 <span data-ttu-id="110a3-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="110a3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="110a3-117">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="110a3-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="110a3-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="110a3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="110a3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="110a3-119">See also</span></span>
- [<span data-ttu-id="110a3-120">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="110a3-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
