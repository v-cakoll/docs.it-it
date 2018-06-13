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
ms.openlocfilehash: de120516655c1a0578e88ecc2890701ed9fc2f6d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443700"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="b4cc2-102">Enumerazione AssemblyRefFlags</span><span class="sxs-lookup"><span data-stu-id="b4cc2-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="b4cc2-103">Contiene valori che descrivono le funzionalità di un riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="b4cc2-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4cc2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4cc2-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b4cc2-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b4cc2-105">Members</span></span>  
  
|<span data-ttu-id="b4cc2-106">Membro</span><span class="sxs-lookup"><span data-stu-id="b4cc2-106">Member</span></span>|<span data-ttu-id="b4cc2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4cc2-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="b4cc2-108">Specifica che il riferimento all'assembly contiene completa, senza hash informazioni sull'autore dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b4cc2-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4cc2-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b4cc2-109">Requirements</span></span>  
 <span data-ttu-id="b4cc2-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4cc2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4cc2-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b4cc2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4cc2-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4cc2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4cc2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4cc2-113">See Also</span></span>  
 [<span data-ttu-id="b4cc2-114">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="b4cc2-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="b4cc2-115">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="b4cc2-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="b4cc2-116">Metodo DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="b4cc2-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
