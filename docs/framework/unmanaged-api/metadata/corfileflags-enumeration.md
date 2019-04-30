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
ms.openlocfilehash: 076d5de3e9d1925e3a030fee4a06a89862105897
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045864"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="3c6ee-102">Enumerazione CorFileFlags</span><span class="sxs-lookup"><span data-stu-id="3c6ee-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="3c6ee-103">Contiene valori che descrivono il tipo di file definito in una chiamata a [IMetaDataAssemblyEmit:: DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="3c6ee-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c6ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c6ee-104">Syntax</span></span>  
  
```  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3c6ee-105">Membri</span><span class="sxs-lookup"><span data-stu-id="3c6ee-105">Members</span></span>  
  
|<span data-ttu-id="3c6ee-106">Member</span><span class="sxs-lookup"><span data-stu-id="3c6ee-106">Member</span></span>|<span data-ttu-id="3c6ee-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c6ee-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="3c6ee-108">Indica che il file non è un file di risorse.</span><span class="sxs-lookup"><span data-stu-id="3c6ee-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="3c6ee-109">Indica che il file, probabilmente è un file di risorse, non contiene metadati.</span><span class="sxs-lookup"><span data-stu-id="3c6ee-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c6ee-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3c6ee-110">Requirements</span></span>  
 <span data-ttu-id="3c6ee-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c6ee-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c6ee-112">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="3c6ee-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3c6ee-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c6ee-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c6ee-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c6ee-114">See also</span></span>

- [<span data-ttu-id="3c6ee-115">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="3c6ee-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
