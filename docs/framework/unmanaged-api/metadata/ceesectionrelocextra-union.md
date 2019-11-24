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
ms.openlocfilehash: 7becace679b62a635d8231c3d42213f247f44190
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444169"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="f6539-102">Unione CeeSectionRelocExtra</span><span class="sxs-lookup"><span data-stu-id="f6539-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="f6539-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span><span class="sxs-lookup"><span data-stu-id="f6539-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6539-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6539-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="f6539-105">Members</span><span class="sxs-lookup"><span data-stu-id="f6539-105">Members</span></span>  
  
|<span data-ttu-id="f6539-106">Member</span><span class="sxs-lookup"><span data-stu-id="f6539-106">Member</span></span>|<span data-ttu-id="f6539-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6539-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="f6539-108">The upper address adjustment for the section.</span><span class="sxs-lookup"><span data-stu-id="f6539-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f6539-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f6539-109">Requirements</span></span>  
 <span data-ttu-id="f6539-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6539-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6539-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f6539-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f6539-112">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f6539-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6539-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6539-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6539-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6539-114">See also</span></span>

- [<span data-ttu-id="f6539-115">Unioni di metadati</span><span class="sxs-lookup"><span data-stu-id="f6539-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
