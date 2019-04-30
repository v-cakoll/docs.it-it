---
title: Enumerazione CorSetENC
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fd903cb4a9ce664b7a1c958a3fef0c639d6845d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045318"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="4e187-102">Enumerazione CorSetENC</span><span class="sxs-lookup"><span data-stu-id="4e187-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="4e187-103">Contiene valori usati per influenzare il comportamento durante la generazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="4e187-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e187-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e187-104">Syntax</span></span>  
  
```  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a><span data-ttu-id="4e187-105">Membri</span><span class="sxs-lookup"><span data-stu-id="4e187-105">Members</span></span>  
  
|<span data-ttu-id="4e187-106">Member</span><span class="sxs-lookup"><span data-stu-id="4e187-106">Member</span></span>|<span data-ttu-id="4e187-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e187-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="4e187-108">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="4e187-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="4e187-109">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="4e187-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="4e187-110">Indica che, mentre i metadati possono essere aggiornati, i token non è possibile spostare.</span><span class="sxs-lookup"><span data-stu-id="4e187-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="4e187-111">Indica che i token possono essere spostati durante gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="4e187-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="4e187-112">Indica che gli aggiornamenti possono essere costituito solo da aggiunte.</span><span class="sxs-lookup"><span data-stu-id="4e187-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="4e187-113">Token non possono essere spostati.</span><span class="sxs-lookup"><span data-stu-id="4e187-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="4e187-114">Indica che la compilazione incrementale.</span><span class="sxs-lookup"><span data-stu-id="4e187-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="4e187-115">Indica che solo i metadati modificati devono essere salvati.</span><span class="sxs-lookup"><span data-stu-id="4e187-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="4e187-116">Include `MDUpdateENC`, `MDUpdateFull` e `MDUpdateIncremental`.</span><span class="sxs-lookup"><span data-stu-id="4e187-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e187-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4e187-117">Requirements</span></span>  
 <span data-ttu-id="4e187-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e187-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e187-119">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="4e187-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4e187-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e187-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e187-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e187-121">See also</span></span>

- [<span data-ttu-id="4e187-122">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="4e187-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
