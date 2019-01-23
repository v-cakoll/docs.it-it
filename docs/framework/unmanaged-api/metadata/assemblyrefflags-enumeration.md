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
ms.openlocfilehash: b31df454c49ddccc74a7e877c09efa4f45b69d9e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491794"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="f71e1-102">Enumerazione AssemblyRefFlags</span><span class="sxs-lookup"><span data-stu-id="f71e1-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="f71e1-103">Contiene valori che descrivono le funzionalità di un riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="f71e1-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f71e1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f71e1-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="f71e1-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f71e1-105">Members</span></span>  
  
|<span data-ttu-id="f71e1-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f71e1-106">Member</span></span>|<span data-ttu-id="f71e1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f71e1-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="f71e1-108">Specifica che il riferimento all'assembly contiene le informazioni complete, senza hash sul server di pubblicazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f71e1-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f71e1-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f71e1-109">Requirements</span></span>  
 <span data-ttu-id="f71e1-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f71e1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f71e1-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f71e1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f71e1-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f71e1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f71e1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f71e1-113">See also</span></span>
- [<span data-ttu-id="f71e1-114">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="f71e1-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="f71e1-115">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="f71e1-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="f71e1-116">Metodo DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="f71e1-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
