---
title: Enumerazione AssemblyRefFlags
ms.date: 03/30/2017
api_name:
- AssemblyRefFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyRefFlags
helpviewer_keywords:
- AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc98b2421d23ffd6dfb716a8cc782b46a9d59ce0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128896"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="6bc9e-102">Enumerazione AssemblyRefFlags</span><span class="sxs-lookup"><span data-stu-id="6bc9e-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="6bc9e-103">Contiene valori che descrivono le funzionalità di un riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="6bc9e-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bc9e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6bc9e-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6bc9e-105">Membri</span><span class="sxs-lookup"><span data-stu-id="6bc9e-105">Members</span></span>  
  
|<span data-ttu-id="6bc9e-106">Member</span><span class="sxs-lookup"><span data-stu-id="6bc9e-106">Member</span></span>|<span data-ttu-id="6bc9e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6bc9e-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="6bc9e-108">Specifica che il riferimento all'assembly contiene le informazioni complete, senza hash sul server di pubblicazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="6bc9e-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6bc9e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6bc9e-109">Requirements</span></span>  
 <span data-ttu-id="6bc9e-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bc9e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bc9e-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6bc9e-111">**Header:** Cor.h</span></span>  
  
 **<span data-ttu-id="6bc9e-112">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6bc9e-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6bc9e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bc9e-113">See also</span></span>

- [<span data-ttu-id="6bc9e-114">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="6bc9e-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="6bc9e-115">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="6bc9e-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="6bc9e-116">Metodo DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="6bc9e-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
