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
ms.openlocfilehash: 8a78a4b82d0b2064c90c938a8614b0c7594f7856
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182273"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="67e76-102">Unione CeeSectionRelocExtra</span><span class="sxs-lookup"><span data-stu-id="67e76-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="67e76-103">Rappresenta un offset di indirizzo che viene usato per il [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interfaccia per rilocare una sezione.</span><span class="sxs-lookup"><span data-stu-id="67e76-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67e76-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67e76-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="67e76-105">Membri</span><span class="sxs-lookup"><span data-stu-id="67e76-105">Members</span></span>  
  
|<span data-ttu-id="67e76-106">Member</span><span class="sxs-lookup"><span data-stu-id="67e76-106">Member</span></span>|<span data-ttu-id="67e76-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67e76-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="67e76-108">La regolazione di indirizzi superiore per la sezione.</span><span class="sxs-lookup"><span data-stu-id="67e76-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67e76-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="67e76-109">Requirements</span></span>  
 <span data-ttu-id="67e76-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67e76-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67e76-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="67e76-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="67e76-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="67e76-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="67e76-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="67e76-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="67e76-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67e76-114">See also</span></span>

- [<span data-ttu-id="67e76-115">Unioni di metadati</span><span class="sxs-lookup"><span data-stu-id="67e76-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
