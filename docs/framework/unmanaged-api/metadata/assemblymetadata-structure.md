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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83f6190872ecf4435688f3b7c82a61f5f15d9f62
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443326"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="f2cbe-102">Struttura ASSEMBLYMETADATA</span><span class="sxs-lookup"><span data-stu-id="f2cbe-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="f2cbe-103">Contiene informazioni sull'assembly di riferimento, tra cui la versione e il livello di supporto per le impostazioni locali, processori e sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2cbe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2cbe-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="f2cbe-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f2cbe-105">Members</span></span>  
  
|<span data-ttu-id="f2cbe-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f2cbe-106">Member</span></span>|<span data-ttu-id="f2cbe-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2cbe-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="f2cbe-108">Il numero di versione principale dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="f2cbe-109">Questo valore non può essere zero.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-109">This value cannot be zero.</span></span> <span data-ttu-id="f2cbe-110">Se tutti i bit di `usMajorVersion` sono impostati, la versione principale non è specificata.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="f2cbe-111">Il numero di versione secondaria dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="f2cbe-112">Questo valore non può essere zero.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-112">This value cannot be zero.</span></span> <span data-ttu-id="f2cbe-113">Se tutti i bit di `usMinorVersion` sono impostati, la versione secondaria non è specificata.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="f2cbe-114">Il numero di build dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="f2cbe-115">Questo valore non può essere zero.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-115">This value cannot be zero.</span></span> <span data-ttu-id="f2cbe-116">Se tutti i bit di `usBuildNumber` sono impostati, il numero di build non è specificato.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="f2cbe-117">Il numero di revisione dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="f2cbe-118">Questo valore non può essere zero.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-118">This value cannot be zero.</span></span> <span data-ttu-id="f2cbe-119">Se tutti i bit di `usRevisionNumber` sono impostati, non viene specificato il numero di revisione.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="f2cbe-120">Un elenco di nomi delle impostazioni locali conformi alle specifiche RFC1766, separati da punti e virgola, che specifica le impostazioni locali supportate dall'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="f2cbe-121">Un valore null indica l'indipendenza dalle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-121">A null value indicates locale independence.</span></span> <span data-ttu-id="f2cbe-122">**Nota:** In .NET Framework versione 1.0 non è possibile specificare più di una delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="f2cbe-123">La dimensione in caratteri "wide" di `szLocale`.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="f2cbe-124">Matrice di identificatori, come definito in Winnt. h, per i tipi di processore supportati da assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="f2cbe-125">Un valore NULL indica l'indipendenza del processore.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="f2cbe-126">La lunghezza del `rdwProcessor` matrice.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="f2cbe-127">Matrice di [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) istanze che specifica i sistemi operativi supportati da assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-127">An array of [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="f2cbe-128">Un valore NULL indica l'indipendenza del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="f2cbe-129">La lunghezza del `rOS` matrice.</span><span class="sxs-lookup"><span data-stu-id="f2cbe-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2cbe-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f2cbe-130">Requirements</span></span>  
 <span data-ttu-id="f2cbe-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2cbe-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2cbe-132">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f2cbe-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2cbe-133">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f2cbe-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f2cbe-134">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2cbe-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2cbe-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2cbe-135">See Also</span></span>  
 [<span data-ttu-id="f2cbe-136">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="f2cbe-136">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="f2cbe-137">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="f2cbe-137">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="f2cbe-138">Struttura OSINFO</span><span class="sxs-lookup"><span data-stu-id="f2cbe-138">OSINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
