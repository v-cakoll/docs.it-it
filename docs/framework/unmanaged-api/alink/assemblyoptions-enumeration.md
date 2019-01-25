---
title: Enumerazione AssemblyOptions
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 939e815f4d3adc5f6e1c8b8fc85c9f4b89372501
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571483"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="c5def-102">Enumerazione AssemblyOptions</span><span class="sxs-lookup"><span data-stu-id="c5def-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="c5def-103">Enumera le opzioni di assembly.</span><span class="sxs-lookup"><span data-stu-id="c5def-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5def-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5def-104">Syntax</span></span>  
  
```  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a><span data-ttu-id="c5def-105">Campi</span><span class="sxs-lookup"><span data-stu-id="c5def-105">Fields</span></span>  
  
|<span data-ttu-id="c5def-106">Campo</span><span class="sxs-lookup"><span data-stu-id="c5def-106">Field</span></span>|<span data-ttu-id="c5def-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5def-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c5def-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="c5def-108">optAssemTitle</span></span>|<span data-ttu-id="c5def-109">Stringa - rappresenta il titolo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c5def-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="c5def-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="c5def-110">optAssemDescription</span></span>|<span data-ttu-id="c5def-111">Stringa - contiene la descrizione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c5def-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="c5def-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="c5def-112">optAssemConfig</span></span>|<span data-ttu-id="c5def-113">Stringa - contiene la configurazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c5def-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="c5def-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="c5def-114">optAssemOS</span></span>|<span data-ttu-id="c5def-115">Stringa, codificata come: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="c5def-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="c5def-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="c5def-116">optAssemProcessor</span></span>|<span data-ttu-id="c5def-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="c5def-117">ULONG</span></span>|  
|<span data-ttu-id="c5def-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="c5def-118">optAssemLocale</span></span>|<span data-ttu-id="c5def-119">Stringa - contiene le impostazioni locali di assembly.</span><span class="sxs-lookup"><span data-stu-id="c5def-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="c5def-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="c5def-120">optAssemVersion</span></span>|<span data-ttu-id="c5def-121">Stringa, codificata come: "Revisione".</span><span class="sxs-lookup"><span data-stu-id="c5def-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="c5def-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="c5def-122">optAssemCompany</span></span>|<span data-ttu-id="c5def-123">Stringa - contiene l'azienda.</span><span class="sxs-lookup"><span data-stu-id="c5def-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="c5def-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="c5def-124">optAssemProduct</span></span>|<span data-ttu-id="c5def-125">Stringa - contiene il nome del prodotto.</span><span class="sxs-lookup"><span data-stu-id="c5def-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="c5def-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="c5def-126">optAssemProductVersion</span></span>|<span data-ttu-id="c5def-127">Stringa (anche nota come InformationalVersion).</span><span class="sxs-lookup"><span data-stu-id="c5def-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="c5def-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="c5def-128">optAssemCopyright</span></span>|<span data-ttu-id="c5def-129">Stringa - contiene le informazioni sul copyright.</span><span class="sxs-lookup"><span data-stu-id="c5def-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="c5def-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="c5def-130">optAssemTrademark</span></span>|<span data-ttu-id="c5def-131">Stringa - contiene le informazioni sul marchio.</span><span class="sxs-lookup"><span data-stu-id="c5def-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="c5def-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="c5def-132">optAssemKeyFile</span></span>|<span data-ttu-id="c5def-133">String (nome file).</span><span class="sxs-lookup"><span data-stu-id="c5def-133">String (file name).</span></span>|  
|<span data-ttu-id="c5def-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="c5def-134">optAssemKeyName</span></span>|<span data-ttu-id="c5def-135">Stringa (il nome della chiave).</span><span class="sxs-lookup"><span data-stu-id="c5def-135">String (The key name).</span></span>|  
|<span data-ttu-id="c5def-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="c5def-136">optAssemAlgID</span></span>|<span data-ttu-id="c5def-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="c5def-137">ULONG</span></span>|  
|<span data-ttu-id="c5def-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="c5def-138">optAssemFlags</span></span>|<span data-ttu-id="c5def-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="c5def-139">ULONG</span></span>|  
|<span data-ttu-id="c5def-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="c5def-140">optAssemHalfSign</span></span>|<span data-ttu-id="c5def-141">Bool (noto anche come DelaySign).</span><span class="sxs-lookup"><span data-stu-id="c5def-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="c5def-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="c5def-142">optAssemFileVersion</span></span>|<span data-ttu-id="c5def-143">Stringa - codificato come "Revisione", identico ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="c5def-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="c5def-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="c5def-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="c5def-145">Stringa - codificato come "Revisione".</span><span class="sxs-lookup"><span data-stu-id="c5def-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="c5def-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="c5def-146">optLastAssemOption</span></span>|<span data-ttu-id="c5def-147">Un contatore del numero di elementi.</span><span class="sxs-lookup"><span data-stu-id="c5def-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c5def-148">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c5def-148">Requirements</span></span>  
 <span data-ttu-id="c5def-149">**Intestazione:** alink.h</span><span class="sxs-lookup"><span data-stu-id="c5def-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="c5def-150">**Libreria**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="c5def-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5def-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5def-151">See also</span></span>
- [<span data-ttu-id="c5def-152">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="c5def-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
