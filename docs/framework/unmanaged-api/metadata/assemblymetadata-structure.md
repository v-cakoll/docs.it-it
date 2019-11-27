---
title: Struttura ASSEMBLYMETADATA
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
ms.openlocfilehash: 24ec1f7d553a59425f7eb02af8e91010d940eb07
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444263"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="c2ea5-102">Struttura ASSEMBLYMETADATA</span><span class="sxs-lookup"><span data-stu-id="c2ea5-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="c2ea5-103">Contiene informazioni sull'assembly a cui si fa riferimento, incluse la versione e il livello di supporto per le impostazioni locali, i processori e i sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2ea5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2ea5-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a><span data-ttu-id="c2ea5-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c2ea5-105">Members</span></span>  
  
|<span data-ttu-id="c2ea5-106">Membro</span><span class="sxs-lookup"><span data-stu-id="c2ea5-106">Member</span></span>|<span data-ttu-id="c2ea5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2ea5-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="c2ea5-108">Numero di versione principale dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="c2ea5-109">Questo valore non può essere zero.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-109">This value cannot be zero.</span></span> <span data-ttu-id="c2ea5-110">Se vengono impostati tutti i bit di `usMajorVersion`, la versione principale non è specificata.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="c2ea5-111">Numero della versione secondaria dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="c2ea5-112">Questo valore non può essere zero.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-112">This value cannot be zero.</span></span> <span data-ttu-id="c2ea5-113">Se vengono impostati tutti i bit di `usMinorVersion`, non viene specificata la versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="c2ea5-114">Numero di build dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="c2ea5-115">Questo valore non può essere zero.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-115">This value cannot be zero.</span></span> <span data-ttu-id="c2ea5-116">Se vengono impostati tutti i bit di `usBuildNumber`, il numero di build non viene specificato.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="c2ea5-117">Numero di revisione dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="c2ea5-118">Questo valore non può essere zero.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-118">This value cannot be zero.</span></span> <span data-ttu-id="c2ea5-119">Se vengono impostati tutti i bit di `usRevisionNumber`, il numero di revisione non viene specificato.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="c2ea5-120">Elenco di nomi delle impostazioni locali conformi alla specifica RFC1766, separati da punti e virgola, che specificano le impostazioni locali supportate dall'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="c2ea5-121">Un valore null indica l'indipendenza delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-121">A null value indicates locale independence.</span></span> <span data-ttu-id="c2ea5-122">**Nota:**  In .NET Framework versione 1,0 non è possibile specificare più di un'impostazione locale.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="c2ea5-123">Dimensioni in caratteri wide di `szLocale`.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="c2ea5-124">Matrice di identificatori, in base a quanto definito in Winnt. h, per i tipi di processore supportati dall'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="c2ea5-125">Un valore NULL indica l'indipendenza del processore.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="c2ea5-126">Lunghezza della matrice di `rdwProcessor`.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="c2ea5-127">Matrice di istanze di [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) che specifica i sistemi operativi supportati dall'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-127">An array of [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="c2ea5-128">Un valore NULL indica l'indipendenza del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="c2ea5-129">Lunghezza della matrice di `rOS`.</span><span class="sxs-lookup"><span data-stu-id="c2ea5-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2ea5-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2ea5-130">Requirements</span></span>  
 <span data-ttu-id="c2ea5-131">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2ea5-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2ea5-132">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c2ea5-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2ea5-133">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c2ea5-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2ea5-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2ea5-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2ea5-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2ea5-135">See also</span></span>

- [<span data-ttu-id="c2ea5-136">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="c2ea5-136">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="c2ea5-137">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="c2ea5-137">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="c2ea5-138">Struttura OSINFO</span><span class="sxs-lookup"><span data-stu-id="c2ea5-138">OSINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
