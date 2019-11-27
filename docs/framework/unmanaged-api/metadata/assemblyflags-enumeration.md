---
title: AssemblyFlags Enumeration
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
ms.openlocfilehash: ffb5953c843a338b4548253457a0c3b1ca0c20f5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444307"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="71e26-102">AssemblyFlags Enumeration</span><span class="sxs-lookup"><span data-stu-id="71e26-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="71e26-103">Contiene valori che descrivono le funzionalità di run-time di un assembly.</span><span class="sxs-lookup"><span data-stu-id="71e26-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71e26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71e26-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="71e26-105">Members</span><span class="sxs-lookup"><span data-stu-id="71e26-105">Members</span></span>  
  
|<span data-ttu-id="71e26-106">Membro</span><span class="sxs-lookup"><span data-stu-id="71e26-106">Member</span></span>|<span data-ttu-id="71e26-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71e26-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="71e26-108">Specifica che le definizioni dei tipi esportati sono implicite all'interno dei file che costituiscono l'assembly.</span><span class="sxs-lookup"><span data-stu-id="71e26-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="71e26-109">In .NET Framework versioni 1,0 e 1,1, questo valore viene sempre impostato.</span><span class="sxs-lookup"><span data-stu-id="71e26-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="71e26-110">Specifica che le definizioni delle risorse sono implicite all'interno dei file che costituiscono l'assembly.</span><span class="sxs-lookup"><span data-stu-id="71e26-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="71e26-111">In .NET Framework 1,0 e 1,1, questo valore viene sempre impostato.</span><span class="sxs-lookup"><span data-stu-id="71e26-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="71e26-112">Specifica che l'assembly non può essere eseguito con altre versioni se sono in esecuzione nello stesso dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="71e26-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="71e26-113">Specifica che l'assembly non può essere eseguito con altre versioni se sono in esecuzione nello stesso processo.</span><span class="sxs-lookup"><span data-stu-id="71e26-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="71e26-114">Specifica che l'assembly non può essere eseguito con altre versioni se sono in esecuzione nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="71e26-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71e26-115">Note</span><span class="sxs-lookup"><span data-stu-id="71e26-115">Remarks</span></span>  
 <span data-ttu-id="71e26-116">I valori compresi tra 0x0010 e 0x0070, inclusi, vengono utilizzati per descrivere le funzionalità di compatibilità affiancata dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="71e26-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="71e26-117">Se nessuno di questi valori è impostato, si presuppone che l'assembly sia compatibile side-by-side.</span><span class="sxs-lookup"><span data-stu-id="71e26-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71e26-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71e26-118">Requirements</span></span>  
 <span data-ttu-id="71e26-119">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71e26-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71e26-120">**Intestazione:** MsCorEE. h</span><span class="sxs-lookup"><span data-stu-id="71e26-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="71e26-121">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="71e26-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="71e26-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71e26-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71e26-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71e26-123">See also</span></span>

- [<span data-ttu-id="71e26-124">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="71e26-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="71e26-125">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="71e26-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
