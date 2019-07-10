---
title: Unione CeeSectionRelocExtra
ms.date: 03/30/2017
api_name:
- CeeSectionRelocExtra Union
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocExtra
helpviewer_keywords:
- CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c2e73caa3c69090bca30c8d4a907ddb619bd0ed4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776328"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="0bc02-102">Unione CeeSectionRelocExtra</span><span class="sxs-lookup"><span data-stu-id="0bc02-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="0bc02-103">Rappresenta un offset di indirizzo che viene usato per il [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interfaccia per rilocare una sezione.</span><span class="sxs-lookup"><span data-stu-id="0bc02-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bc02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0bc02-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="0bc02-105">Membri</span><span class="sxs-lookup"><span data-stu-id="0bc02-105">Members</span></span>  
  
|<span data-ttu-id="0bc02-106">Member</span><span class="sxs-lookup"><span data-stu-id="0bc02-106">Member</span></span>|<span data-ttu-id="0bc02-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0bc02-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="0bc02-108">La regolazione di indirizzi superiore per la sezione.</span><span class="sxs-lookup"><span data-stu-id="0bc02-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0bc02-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0bc02-109">Requirements</span></span>  
 <span data-ttu-id="0bc02-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bc02-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bc02-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0bc02-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0bc02-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0bc02-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0bc02-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bc02-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bc02-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bc02-114">See also</span></span>

- [<span data-ttu-id="0bc02-115">Unioni di metadati</span><span class="sxs-lookup"><span data-stu-id="0bc02-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
