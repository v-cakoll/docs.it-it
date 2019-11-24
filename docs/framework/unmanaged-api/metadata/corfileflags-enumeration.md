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
ms.openlocfilehash: c315e2ae2753b59b4e277764d27c3fb3388b515c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445424"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="3aaa6-102">Enumerazione CorFileFlags</span><span class="sxs-lookup"><span data-stu-id="3aaa6-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="3aaa6-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="3aaa6-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aaa6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3aaa6-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3aaa6-105">Members</span><span class="sxs-lookup"><span data-stu-id="3aaa6-105">Members</span></span>  
  
|<span data-ttu-id="3aaa6-106">Member</span><span class="sxs-lookup"><span data-stu-id="3aaa6-106">Member</span></span>|<span data-ttu-id="3aaa6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3aaa6-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="3aaa6-108">Indicates that the file is not a resource file.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="3aaa6-109">Indicates that the file, possibly a resource file, does not contain metadata.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3aaa6-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3aaa6-110">Requirements</span></span>  
 <span data-ttu-id="3aaa6-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3aaa6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3aaa6-112">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="3aaa6-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3aaa6-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3aaa6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aaa6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3aaa6-114">See also</span></span>

- [<span data-ttu-id="3aaa6-115">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="3aaa6-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
