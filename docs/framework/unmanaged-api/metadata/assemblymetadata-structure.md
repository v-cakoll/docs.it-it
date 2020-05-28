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
ms.openlocfilehash: 5c7211fc2523b70313a1e4d4d9d2da0dcecd1d32
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009431"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="49f69-102">Struttura ASSEMBLYMETADATA</span><span class="sxs-lookup"><span data-stu-id="49f69-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="49f69-103">Contiene informazioni sull'assembly a cui si fa riferimento, incluse la versione e il livello di supporto per le impostazioni locali, i processori e i sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="49f69-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49f69-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49f69-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="49f69-105">Membri</span><span class="sxs-lookup"><span data-stu-id="49f69-105">Members</span></span>  
  
|<span data-ttu-id="49f69-106">Membro</span><span class="sxs-lookup"><span data-stu-id="49f69-106">Member</span></span>|<span data-ttu-id="49f69-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49f69-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="49f69-108">Numero di versione principale dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="49f69-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="49f69-109">Questo valore non può essere zero.</span><span class="sxs-lookup"><span data-stu-id="49f69-109">This value cannot be zero.</span></span> <span data-ttu-id="49f69-110">Se tutti i bit di `usMajorVersion` sono impostati, la versione principale non è specificata.</span><span class="sxs-lookup"><span data-stu-id="49f69-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="49f69-111">Numero della versione secondaria dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="49f69-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="49f69-112">Questo valore non può essere zero.</span><span class="sxs-lookup"><span data-stu-id="49f69-112">This value cannot be zero.</span></span> <span data-ttu-id="49f69-113">Se tutti i bit di `usMinorVersion` sono impostati, la versione secondaria non è specificata.</span><span class="sxs-lookup"><span data-stu-id="49f69-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="49f69-114">Numero di build dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="49f69-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="49f69-115">Questo valore non può essere zero.</span><span class="sxs-lookup"><span data-stu-id="49f69-115">This value cannot be zero.</span></span> <span data-ttu-id="49f69-116">Se tutti i bit di `usBuildNumber` sono impostati, il numero di build non viene specificato.</span><span class="sxs-lookup"><span data-stu-id="49f69-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="49f69-117">Numero di revisione dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="49f69-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="49f69-118">Questo valore non può essere zero.</span><span class="sxs-lookup"><span data-stu-id="49f69-118">This value cannot be zero.</span></span> <span data-ttu-id="49f69-119">Se tutti i bit di `usRevisionNumber` sono impostati, il numero di revisione non viene specificato.</span><span class="sxs-lookup"><span data-stu-id="49f69-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="49f69-120">Elenco di nomi delle impostazioni locali conformi alla specifica RFC1766, separati da punti e virgola, che specificano le impostazioni locali supportate dall'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="49f69-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="49f69-121">Un valore null indica l'indipendenza delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="49f69-121">A null value indicates locale independence.</span></span> <span data-ttu-id="49f69-122">**Nota:**  In .NET Framework versione 1,0 non è possibile specificare più di un'impostazione locale.</span><span class="sxs-lookup"><span data-stu-id="49f69-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="49f69-123">Dimensioni in caratteri wide di `szLocale` .</span><span class="sxs-lookup"><span data-stu-id="49f69-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="49f69-124">Matrice di identificatori, in base a quanto definito in Winnt. h, per i tipi di processore supportati dall'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="49f69-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="49f69-125">Un valore NULL indica l'indipendenza del processore.</span><span class="sxs-lookup"><span data-stu-id="49f69-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="49f69-126">Lunghezza della matrice `rdwProcessor`.</span><span class="sxs-lookup"><span data-stu-id="49f69-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="49f69-127">Matrice di istanze di [OSINFO](osinfo-structure.md) che specifica i sistemi operativi supportati dall'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="49f69-127">An array of [OSINFO](osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="49f69-128">Un valore NULL indica l'indipendenza del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="49f69-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="49f69-129">Lunghezza della matrice `rOS`.</span><span class="sxs-lookup"><span data-stu-id="49f69-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49f69-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49f69-130">Requirements</span></span>  
 <span data-ttu-id="49f69-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49f69-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49f69-132">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="49f69-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49f69-133">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="49f69-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49f69-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49f69-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f69-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49f69-135">See also</span></span>

- [<span data-ttu-id="49f69-136">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="49f69-136">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="49f69-137">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="49f69-137">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="49f69-138">Struttura OSINFO</span><span class="sxs-lookup"><span data-stu-id="49f69-138">OSINFO Structure</span></span>](osinfo-structure.md)
