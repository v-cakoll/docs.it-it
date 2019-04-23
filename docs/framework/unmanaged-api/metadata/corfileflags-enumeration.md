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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159614"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="6fa71-102">Enumerazione CorFileFlags</span><span class="sxs-lookup"><span data-stu-id="6fa71-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="6fa71-103">Contiene valori che descrivono il tipo di file definito in una chiamata a [IMetaDataAssemblyEmit:: DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="6fa71-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fa71-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6fa71-104">Syntax</span></span>  
  
```  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6fa71-105">Membri</span><span class="sxs-lookup"><span data-stu-id="6fa71-105">Members</span></span>  
  
|<span data-ttu-id="6fa71-106">Member</span><span class="sxs-lookup"><span data-stu-id="6fa71-106">Member</span></span>|<span data-ttu-id="6fa71-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6fa71-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="6fa71-108">Indica che il file non è un file di risorse.</span><span class="sxs-lookup"><span data-stu-id="6fa71-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="6fa71-109">Indica che il file, probabilmente è un file di risorse, non contiene metadati.</span><span class="sxs-lookup"><span data-stu-id="6fa71-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6fa71-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6fa71-110">Requirements</span></span>  
 <span data-ttu-id="6fa71-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fa71-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fa71-112">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="6fa71-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6fa71-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fa71-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fa71-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fa71-114">See also</span></span>

- [<span data-ttu-id="6fa71-115">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="6fa71-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
