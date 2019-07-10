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
ms.openlocfilehash: 324e30f6cbcaa1d1d81c7c03967dbb629d2cd6e9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742273"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="a83d1-102">Enumerazione AssemblyOptions</span><span class="sxs-lookup"><span data-stu-id="a83d1-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="a83d1-103">Enumera le opzioni di assembly.</span><span class="sxs-lookup"><span data-stu-id="a83d1-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a83d1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a83d1-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="fields"></a><span data-ttu-id="a83d1-105">Campi</span><span class="sxs-lookup"><span data-stu-id="a83d1-105">Fields</span></span>  
  
|<span data-ttu-id="a83d1-106">Campo</span><span class="sxs-lookup"><span data-stu-id="a83d1-106">Field</span></span>|<span data-ttu-id="a83d1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a83d1-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a83d1-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="a83d1-108">optAssemTitle</span></span>|<span data-ttu-id="a83d1-109">Stringa - rappresenta il titolo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a83d1-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="a83d1-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="a83d1-110">optAssemDescription</span></span>|<span data-ttu-id="a83d1-111">Stringa - contiene la descrizione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a83d1-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="a83d1-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="a83d1-112">optAssemConfig</span></span>|<span data-ttu-id="a83d1-113">Stringa - contiene la configurazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a83d1-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="a83d1-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="a83d1-114">optAssemOS</span></span>|<span data-ttu-id="a83d1-115">Stringa, codificata come: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="a83d1-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="a83d1-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="a83d1-116">optAssemProcessor</span></span>|<span data-ttu-id="a83d1-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="a83d1-117">ULONG</span></span>|  
|<span data-ttu-id="a83d1-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="a83d1-118">optAssemLocale</span></span>|<span data-ttu-id="a83d1-119">Stringa - contiene le impostazioni locali di assembly.</span><span class="sxs-lookup"><span data-stu-id="a83d1-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="a83d1-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="a83d1-120">optAssemVersion</span></span>|<span data-ttu-id="a83d1-121">Stringa, codificata come: "Revisione".</span><span class="sxs-lookup"><span data-stu-id="a83d1-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="a83d1-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="a83d1-122">optAssemCompany</span></span>|<span data-ttu-id="a83d1-123">Stringa - contiene l'azienda.</span><span class="sxs-lookup"><span data-stu-id="a83d1-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="a83d1-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="a83d1-124">optAssemProduct</span></span>|<span data-ttu-id="a83d1-125">Stringa - contiene il nome del prodotto.</span><span class="sxs-lookup"><span data-stu-id="a83d1-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="a83d1-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="a83d1-126">optAssemProductVersion</span></span>|<span data-ttu-id="a83d1-127">Stringa (anche nota come InformationalVersion).</span><span class="sxs-lookup"><span data-stu-id="a83d1-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="a83d1-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="a83d1-128">optAssemCopyright</span></span>|<span data-ttu-id="a83d1-129">Stringa - contiene le informazioni sul copyright.</span><span class="sxs-lookup"><span data-stu-id="a83d1-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="a83d1-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="a83d1-130">optAssemTrademark</span></span>|<span data-ttu-id="a83d1-131">Stringa - contiene le informazioni sul marchio.</span><span class="sxs-lookup"><span data-stu-id="a83d1-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="a83d1-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="a83d1-132">optAssemKeyFile</span></span>|<span data-ttu-id="a83d1-133">String (nome file).</span><span class="sxs-lookup"><span data-stu-id="a83d1-133">String (file name).</span></span>|  
|<span data-ttu-id="a83d1-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="a83d1-134">optAssemKeyName</span></span>|<span data-ttu-id="a83d1-135">Stringa (il nome della chiave).</span><span class="sxs-lookup"><span data-stu-id="a83d1-135">String (The key name).</span></span>|  
|<span data-ttu-id="a83d1-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="a83d1-136">optAssemAlgID</span></span>|<span data-ttu-id="a83d1-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="a83d1-137">ULONG</span></span>|  
|<span data-ttu-id="a83d1-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="a83d1-138">optAssemFlags</span></span>|<span data-ttu-id="a83d1-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="a83d1-139">ULONG</span></span>|  
|<span data-ttu-id="a83d1-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="a83d1-140">optAssemHalfSign</span></span>|<span data-ttu-id="a83d1-141">Bool (noto anche come DelaySign).</span><span class="sxs-lookup"><span data-stu-id="a83d1-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="a83d1-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="a83d1-142">optAssemFileVersion</span></span>|<span data-ttu-id="a83d1-143">Stringa - codificato come "Revisione", identico ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="a83d1-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="a83d1-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="a83d1-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="a83d1-145">Stringa - codificato come "Revisione".</span><span class="sxs-lookup"><span data-stu-id="a83d1-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="a83d1-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="a83d1-146">optLastAssemOption</span></span>|<span data-ttu-id="a83d1-147">Un contatore del numero di elementi.</span><span class="sxs-lookup"><span data-stu-id="a83d1-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a83d1-148">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a83d1-148">Requirements</span></span>  
 <span data-ttu-id="a83d1-149">**Intestazione:** alink.h</span><span class="sxs-lookup"><span data-stu-id="a83d1-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="a83d1-150">**Libreria**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="a83d1-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a83d1-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a83d1-151">See also</span></span>

- [<span data-ttu-id="a83d1-152">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="a83d1-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
