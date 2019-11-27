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
ms.openlocfilehash: 23d293a87112c62cb2127b435faeca258a7de226
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444219"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="03750-102">Enumerazione AssemblyRefFlags</span><span class="sxs-lookup"><span data-stu-id="03750-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="03750-103">Contiene valori che descrivono le funzionalità di un riferimento a un assembly.</span><span class="sxs-lookup"><span data-stu-id="03750-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03750-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03750-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="03750-105">Membri</span><span class="sxs-lookup"><span data-stu-id="03750-105">Members</span></span>  
  
|<span data-ttu-id="03750-106">Membro</span><span class="sxs-lookup"><span data-stu-id="03750-106">Member</span></span>|<span data-ttu-id="03750-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03750-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="03750-108">Specifica che il riferimento all'assembly contiene informazioni complete e senza hash relative al server di pubblicazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="03750-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="03750-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03750-109">Requirements</span></span>  
 <span data-ttu-id="03750-110">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03750-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03750-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="03750-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="03750-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03750-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03750-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03750-113">See also</span></span>

- [<span data-ttu-id="03750-114">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="03750-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="03750-115">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="03750-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="03750-116">Metodo DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="03750-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
