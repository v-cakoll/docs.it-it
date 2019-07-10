---
title: Enumerazione AssemblyFlags
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 502e7841f8c413aa48732bcea0b6c2178d70c061
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776439"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="91f08-102">Enumerazione AssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="91f08-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="91f08-103">Contiene valori che descrivono le funzionalità in fase di esecuzione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="91f08-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91f08-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91f08-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="91f08-105">Membri</span><span class="sxs-lookup"><span data-stu-id="91f08-105">Members</span></span>  
  
|<span data-ttu-id="91f08-106">Member</span><span class="sxs-lookup"><span data-stu-id="91f08-106">Member</span></span>|<span data-ttu-id="91f08-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91f08-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="91f08-108">Specifica che le definizioni dei tipi esportata sono implicite all'interno dei file che costituiscono l'assembly.</span><span class="sxs-lookup"><span data-stu-id="91f08-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="91f08-109">Nelle versioni 1.0 e 1.1 di .NET Framework, questo valore è sempre presuppone che sia impostato.</span><span class="sxs-lookup"><span data-stu-id="91f08-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="91f08-110">Specifica che le definizioni delle risorse sono implicite all'interno dei file che costituiscono l'assembly.</span><span class="sxs-lookup"><span data-stu-id="91f08-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="91f08-111">In .NET Framework 1.0 e 1.1, questo valore è sempre presuppone che sia impostato.</span><span class="sxs-lookup"><span data-stu-id="91f08-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="91f08-112">Specifica che l'assembly non è possibile eseguire con altre versioni se sono in esecuzione nello stesso dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="91f08-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="91f08-113">Specifica che l'assembly non è possibile eseguire con altre versioni se sono in esecuzione nello stesso processo.</span><span class="sxs-lookup"><span data-stu-id="91f08-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="91f08-114">Specifica che l'assembly non è possibile eseguire con le altre versioni se sono in esecuzione nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="91f08-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91f08-115">Note</span><span class="sxs-lookup"><span data-stu-id="91f08-115">Remarks</span></span>  
 <span data-ttu-id="91f08-116">I valori compresi tra 0x0010 e 0x0070, inclusivo, vengono utilizzati per descrivere le funzionalità side-by-side compatibilità dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="91f08-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="91f08-117">Se nessuno di questi valori sono impostate, l'assembly viene considerato compatibile side-by-side.</span><span class="sxs-lookup"><span data-stu-id="91f08-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91f08-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="91f08-118">Requirements</span></span>  
 <span data-ttu-id="91f08-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91f08-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91f08-120">**Intestazione:** MsCorEE.h</span><span class="sxs-lookup"><span data-stu-id="91f08-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="91f08-121">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="91f08-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="91f08-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91f08-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f08-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91f08-123">See also</span></span>

- [<span data-ttu-id="91f08-124">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="91f08-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="91f08-125">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="91f08-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
