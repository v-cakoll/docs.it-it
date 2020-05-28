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
ms.openlocfilehash: 1cb84b94b37a2e9e8dd4d20d09cbca82db290c0f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009452"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="c3bd4-102">Enumerazione AssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="c3bd4-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="c3bd4-103">Contiene valori che descrivono le funzionalità di run-time di un assembly.</span><span class="sxs-lookup"><span data-stu-id="c3bd4-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3bd4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3bd4-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c3bd4-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c3bd4-105">Members</span></span>  
  
|<span data-ttu-id="c3bd4-106">Membro</span><span class="sxs-lookup"><span data-stu-id="c3bd4-106">Member</span></span>|<span data-ttu-id="c3bd4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3bd4-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="c3bd4-108">Specifica che le definizioni dei tipi esportati sono implicite all'interno dei file che costituiscono l'assembly.</span><span class="sxs-lookup"><span data-stu-id="c3bd4-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="c3bd4-109">In .NET Framework versioni 1,0 e 1,1, questo valore viene sempre impostato.</span><span class="sxs-lookup"><span data-stu-id="c3bd4-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="c3bd4-110">Specifica che le definizioni delle risorse sono implicite all'interno dei file che costituiscono l'assembly.</span><span class="sxs-lookup"><span data-stu-id="c3bd4-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="c3bd4-111">In .NET Framework 1,0 e 1,1, questo valore viene sempre impostato.</span><span class="sxs-lookup"><span data-stu-id="c3bd4-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="c3bd4-112">Specifica che l'assembly non può essere eseguito con altre versioni se sono in esecuzione nello stesso dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="c3bd4-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="c3bd4-113">Specifica che l'assembly non può essere eseguito con altre versioni se sono in esecuzione nello stesso processo.</span><span class="sxs-lookup"><span data-stu-id="c3bd4-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="c3bd4-114">Specifica che l'assembly non può essere eseguito con altre versioni se sono in esecuzione nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="c3bd4-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3bd4-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="c3bd4-115">Remarks</span></span>  
 <span data-ttu-id="c3bd4-116">I valori compresi tra 0x0010 e 0x0070, inclusi, vengono utilizzati per descrivere le funzionalità di compatibilità affiancata dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="c3bd4-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="c3bd4-117">Se nessuno di questi valori è impostato, si presuppone che l'assembly sia compatibile side-by-side.</span><span class="sxs-lookup"><span data-stu-id="c3bd4-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3bd4-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3bd4-118">Requirements</span></span>  
 <span data-ttu-id="c3bd4-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3bd4-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3bd4-120">**Intestazione:** MsCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c3bd4-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="c3bd4-121">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c3bd4-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c3bd4-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3bd4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3bd4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3bd4-123">See also</span></span>

- [<span data-ttu-id="c3bd4-124">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="c3bd4-124">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="c3bd4-125">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="c3bd4-125">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
