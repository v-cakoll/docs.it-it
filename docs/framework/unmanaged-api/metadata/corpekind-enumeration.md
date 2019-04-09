---
title: Enumerazione CorPEKind
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d8f830ca7e273b65dc9ec77566a02df6c32cd464
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202391"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="11fe6-102">Enumerazione CorPEKind</span><span class="sxs-lookup"><span data-stu-id="11fe6-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="11fe6-103">Contiene valori che descrivono un file eseguibile portabile (PE), come restituito da una chiamata a [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span><span class="sxs-lookup"><span data-stu-id="11fe6-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11fe6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11fe6-104">Syntax</span></span>  
  
```  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="11fe6-105">Membri</span><span class="sxs-lookup"><span data-stu-id="11fe6-105">Members</span></span>  
  
|<span data-ttu-id="11fe6-106">Member</span><span class="sxs-lookup"><span data-stu-id="11fe6-106">Member</span></span>|<span data-ttu-id="11fe6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11fe6-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="11fe6-108">Indica che questo non è un file PE.</span><span class="sxs-lookup"><span data-stu-id="11fe6-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="11fe6-109">Indica che questo file PE contiene solo codice gestito.</span><span class="sxs-lookup"><span data-stu-id="11fe6-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="11fe6-110">Indica che questo file PE effettua le chiamate a Win32.</span><span class="sxs-lookup"><span data-stu-id="11fe6-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="11fe6-111">Indica che questo file PE viene eseguito su una piattaforma a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="11fe6-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="11fe6-112">Indica che il file PE sia codice nativo.</span><span class="sxs-lookup"><span data-stu-id="11fe6-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="11fe6-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="11fe6-113">pe32BitPreferred</span></span>|<span data-ttu-id="11fe6-114">Indica che il file PE è indipendente dalla piattaforma e preferite per poter essere caricato in un ambiente a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="11fe6-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11fe6-115">Note</span><span class="sxs-lookup"><span data-stu-id="11fe6-115">Remarks</span></span>  
 <span data-ttu-id="11fe6-116">Questi valori possono essere usati nelle combinazioni bit per bit.</span><span class="sxs-lookup"><span data-stu-id="11fe6-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11fe6-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="11fe6-117">Requirements</span></span>  
 <span data-ttu-id="11fe6-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11fe6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11fe6-119">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="11fe6-119">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="11fe6-120">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="11fe6-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="11fe6-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11fe6-121">See also</span></span>

- [<span data-ttu-id="11fe6-122">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="11fe6-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
