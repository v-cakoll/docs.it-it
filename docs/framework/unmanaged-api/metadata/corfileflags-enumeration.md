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
ms.openlocfilehash: c8c2757e99b80204ad52e69a596d62c55c369965
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007416"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="d8166-102">Enumerazione CorFileFlags</span><span class="sxs-lookup"><span data-stu-id="d8166-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="d8166-103">Contiene valori che descrivono il tipo di file definito in una chiamata a [IMetaDataAssemblyEmit::D efinefile](imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="d8166-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8166-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8166-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="d8166-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d8166-105">Members</span></span>  
  
|<span data-ttu-id="d8166-106">Membro</span><span class="sxs-lookup"><span data-stu-id="d8166-106">Member</span></span>|<span data-ttu-id="d8166-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8166-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="d8166-108">Indica che il file non è un file di risorse.</span><span class="sxs-lookup"><span data-stu-id="d8166-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="d8166-109">Indica che il file, possibilmente un file di risorse, non contiene metadati.</span><span class="sxs-lookup"><span data-stu-id="d8166-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8166-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8166-110">Requirements</span></span>  
 <span data-ttu-id="d8166-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8166-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8166-112">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="d8166-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d8166-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8166-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8166-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8166-114">See also</span></span>

- [<span data-ttu-id="d8166-115">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="d8166-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
