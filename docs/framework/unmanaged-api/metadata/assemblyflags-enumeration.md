---
title: Enumerazione AssemblyFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 605817ef23246f708b6cf46a93072cde3003ab43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="033c2-102">Enumerazione AssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="033c2-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="033c2-103">Contiene valori che descrivono le funzionalità in fase di esecuzione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="033c2-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="033c2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="033c2-104">Syntax</span></span>  
  
```  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="033c2-105">Membri</span><span class="sxs-lookup"><span data-stu-id="033c2-105">Members</span></span>  
  
|<span data-ttu-id="033c2-106">Membro</span><span class="sxs-lookup"><span data-stu-id="033c2-106">Member</span></span>|<span data-ttu-id="033c2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="033c2-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="033c2-108">Specifica che le definizioni dei tipi esportata sono implicite all'interno dei file che costituiscono l'assembly.</span><span class="sxs-lookup"><span data-stu-id="033c2-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="033c2-109">Nelle versioni di .NET Framework 1.0 e 1.1, questo valore è sempre presuppone che sia impostato.</span><span class="sxs-lookup"><span data-stu-id="033c2-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="033c2-110">Specifica che le definizioni delle risorse sono implicite all'interno dei file che costituiscono l'assembly.</span><span class="sxs-lookup"><span data-stu-id="033c2-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="033c2-111">In .NET Framework 1.0 e 1.1, questo valore è sempre presuppone che sia impostato.</span><span class="sxs-lookup"><span data-stu-id="033c2-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="033c2-112">Specifica che l'assembly non è possibile eseguire con altre versioni se sono in esecuzione nello stesso dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="033c2-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="033c2-113">Specifica che l'assembly non è possibile eseguire con altre versioni se sono in esecuzione nello stesso processo.</span><span class="sxs-lookup"><span data-stu-id="033c2-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="033c2-114">Specifica che l'assembly non è possibile eseguire con altre versioni se sono in esecuzione nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="033c2-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="033c2-115">Note</span><span class="sxs-lookup"><span data-stu-id="033c2-115">Remarks</span></span>  
 <span data-ttu-id="033c2-116">I valori compresi tra 0x0010 e 0x0070, estremi inclusi, vengono utilizzati per descrivere le funzionalità di compatibilità side-by-side dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="033c2-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="033c2-117">Se viene impostato alcuno di questi valori, l'assembly viene considerato compatibile side-by-side.</span><span class="sxs-lookup"><span data-stu-id="033c2-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="033c2-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="033c2-118">Requirements</span></span>  
 <span data-ttu-id="033c2-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="033c2-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="033c2-120">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="033c2-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="033c2-121">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="033c2-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="033c2-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="033c2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="033c2-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="033c2-123">See Also</span></span>  
 [<span data-ttu-id="033c2-124">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="033c2-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="033c2-125">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="033c2-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
