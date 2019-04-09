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
ms.openlocfilehash: 7c86a4fd2788c8ea2df5d9e54c5c221afd179704
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091421"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="a17d1-102">Enumerazione AssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="a17d1-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="a17d1-103">Contiene valori che descrivono le funzionalità in fase di esecuzione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="a17d1-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a17d1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a17d1-104">Syntax</span></span>  
  
```  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="a17d1-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a17d1-105">Members</span></span>  
  
|<span data-ttu-id="a17d1-106">Member</span><span class="sxs-lookup"><span data-stu-id="a17d1-106">Member</span></span>|<span data-ttu-id="a17d1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a17d1-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="a17d1-108">Specifica che le definizioni dei tipi esportata sono implicite all'interno dei file che costituiscono l'assembly.</span><span class="sxs-lookup"><span data-stu-id="a17d1-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="a17d1-109">Nelle versioni 1.0 e 1.1 di .NET Framework, questo valore è sempre presuppone che sia impostato.</span><span class="sxs-lookup"><span data-stu-id="a17d1-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="a17d1-110">Specifica che le definizioni delle risorse sono implicite all'interno dei file che costituiscono l'assembly.</span><span class="sxs-lookup"><span data-stu-id="a17d1-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="a17d1-111">In .NET Framework 1.0 e 1.1, questo valore è sempre presuppone che sia impostato.</span><span class="sxs-lookup"><span data-stu-id="a17d1-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="a17d1-112">Specifica che l'assembly non è possibile eseguire con altre versioni se sono in esecuzione nello stesso dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="a17d1-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="a17d1-113">Specifica che l'assembly non è possibile eseguire con altre versioni se sono in esecuzione nello stesso processo.</span><span class="sxs-lookup"><span data-stu-id="a17d1-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="a17d1-114">Specifica che l'assembly non è possibile eseguire con le altre versioni se sono in esecuzione nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="a17d1-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a17d1-115">Note</span><span class="sxs-lookup"><span data-stu-id="a17d1-115">Remarks</span></span>  
 <span data-ttu-id="a17d1-116">I valori compresi tra 0x0010 e 0x0070, inclusivo, vengono utilizzati per descrivere le funzionalità side-by-side compatibilità dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="a17d1-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="a17d1-117">Se nessuno di questi valori sono impostate, l'assembly viene considerato compatibile side-by-side.</span><span class="sxs-lookup"><span data-stu-id="a17d1-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a17d1-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a17d1-118">Requirements</span></span>  
 <span data-ttu-id="a17d1-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a17d1-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a17d1-120">**Intestazione:** MsCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a17d1-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="a17d1-121">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a17d1-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="a17d1-122">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a17d1-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a17d1-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a17d1-123">See also</span></span>

- [<span data-ttu-id="a17d1-124">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="a17d1-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="a17d1-125">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="a17d1-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
