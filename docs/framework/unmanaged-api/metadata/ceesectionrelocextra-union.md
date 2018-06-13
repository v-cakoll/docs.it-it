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
ms.openlocfilehash: c7634ec801a30aa7ba07954c1df0c3d37ec279eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440301"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="a3128-102">Unione CeeSectionRelocExtra</span><span class="sxs-lookup"><span data-stu-id="a3128-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="a3128-103">Rappresenta un offset di indirizzo che viene utilizzato il [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interfaccia per rilocare una sezione.</span><span class="sxs-lookup"><span data-stu-id="a3128-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3128-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3128-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="a3128-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a3128-105">Members</span></span>  
  
|<span data-ttu-id="a3128-106">Membro</span><span class="sxs-lookup"><span data-stu-id="a3128-106">Member</span></span>|<span data-ttu-id="a3128-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3128-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="a3128-108">La regolazione di un indirizzo superiore per la sezione.</span><span class="sxs-lookup"><span data-stu-id="a3128-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a3128-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3128-109">Requirements</span></span>  
 <span data-ttu-id="a3128-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3128-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3128-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a3128-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a3128-112">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a3128-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a3128-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3128-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3128-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3128-114">See Also</span></span>  
 [<span data-ttu-id="a3128-115">Unioni di metadati</span><span class="sxs-lookup"><span data-stu-id="a3128-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
