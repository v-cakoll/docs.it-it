---
title: Enumerazione CorFileFlags
ms.date: 03/30/2017
api_name:
- CorFileFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileFlags
helpviewer_keywords:
- CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8a614ad1bd9738c993775667ccd261a089e8b57a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624262"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="d205c-102">Enumerazione CorFileFlags</span><span class="sxs-lookup"><span data-stu-id="d205c-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="d205c-103">Contiene valori che descrivono il tipo di file definito in una chiamata a [IMetaDataAssemblyEmit:: DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="d205c-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d205c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d205c-104">Syntax</span></span>  
  
```  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="d205c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d205c-105">Members</span></span>  
  
|<span data-ttu-id="d205c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="d205c-106">Member</span></span>|<span data-ttu-id="d205c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d205c-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="d205c-108">Indica che il file non è un file di risorse.</span><span class="sxs-lookup"><span data-stu-id="d205c-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="d205c-109">Indica che il file, probabilmente è un file di risorse, non contiene metadati.</span><span class="sxs-lookup"><span data-stu-id="d205c-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d205c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d205c-110">Requirements</span></span>  
 <span data-ttu-id="d205c-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d205c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d205c-112">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="d205c-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d205c-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d205c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d205c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d205c-114">See also</span></span>
- [<span data-ttu-id="d205c-115">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="d205c-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
