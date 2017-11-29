---
title: Unione CeeSectionRelocExtra
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CeeSectionRelocExtra Union
api_location: mscoree.dll
api_type: COM
f1_keywords: CeeSectionRelocExtra
helpviewer_keywords: CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c5b584ced996b31be6656082af3f64a19b1f223c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="bf5b4-102">Unione CeeSectionRelocExtra</span><span class="sxs-lookup"><span data-stu-id="bf5b4-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="bf5b4-103">Rappresenta un offset di indirizzo che viene utilizzato il [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interfaccia per rilocare una sezione.</span><span class="sxs-lookup"><span data-stu-id="bf5b4-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf5b4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf5b4-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="bf5b4-105">Membri</span><span class="sxs-lookup"><span data-stu-id="bf5b4-105">Members</span></span>  
  
|<span data-ttu-id="bf5b4-106">Membro</span><span class="sxs-lookup"><span data-stu-id="bf5b4-106">Member</span></span>|<span data-ttu-id="bf5b4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf5b4-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="bf5b4-108">La regolazione di un indirizzo superiore per la sezione.</span><span class="sxs-lookup"><span data-stu-id="bf5b4-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bf5b4-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bf5b4-109">Requirements</span></span>  
 <span data-ttu-id="bf5b4-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf5b4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf5b4-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bf5b4-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf5b4-112">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bf5b4-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf5b4-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf5b4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf5b4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf5b4-114">See Also</span></span>  
 [<span data-ttu-id="bf5b4-115">Unioni di metadati</span><span class="sxs-lookup"><span data-stu-id="bf5b4-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
