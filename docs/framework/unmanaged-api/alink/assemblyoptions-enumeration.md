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
ms.openlocfilehash: e3926a0d49b2db02cf52a3cc943b05edc4cc36a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406285"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="952d7-102">Enumerazione AssemblyOptions</span><span class="sxs-lookup"><span data-stu-id="952d7-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="952d7-103">Enumera le opzioni di assembly.</span><span class="sxs-lookup"><span data-stu-id="952d7-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="952d7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="952d7-104">Syntax</span></span>  
  
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
  
## <a name="fields"></a><span data-ttu-id="952d7-105">Campi</span><span class="sxs-lookup"><span data-stu-id="952d7-105">Fields</span></span>  
  
|<span data-ttu-id="952d7-106">Campo</span><span class="sxs-lookup"><span data-stu-id="952d7-106">Field</span></span>|<span data-ttu-id="952d7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="952d7-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="952d7-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="952d7-108">optAssemTitle</span></span>|<span data-ttu-id="952d7-109">Stringa - rappresenta il titolo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="952d7-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="952d7-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="952d7-110">optAssemDescription</span></span>|<span data-ttu-id="952d7-111">Stringa - contiene la descrizione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="952d7-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="952d7-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="952d7-112">optAssemConfig</span></span>|<span data-ttu-id="952d7-113">Stringa - contiene la configurazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="952d7-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="952d7-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="952d7-114">optAssemOS</span></span>|<span data-ttu-id="952d7-115">Stringa - codificata come: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="952d7-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="952d7-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="952d7-116">optAssemProcessor</span></span>|<span data-ttu-id="952d7-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="952d7-117">ULONG</span></span>|  
|<span data-ttu-id="952d7-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="952d7-118">optAssemLocale</span></span>|<span data-ttu-id="952d7-119">Stringa - contiene le impostazioni locali di assembly.</span><span class="sxs-lookup"><span data-stu-id="952d7-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="952d7-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="952d7-120">optAssemVersion</span></span>|<span data-ttu-id="952d7-121">Stringa - codificata come: "Principale".</span><span class="sxs-lookup"><span data-stu-id="952d7-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="952d7-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="952d7-122">optAssemCompany</span></span>|<span data-ttu-id="952d7-123">Stringa - contiene la società.</span><span class="sxs-lookup"><span data-stu-id="952d7-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="952d7-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="952d7-124">optAssemProduct</span></span>|<span data-ttu-id="952d7-125">Stringa - contiene il nome del prodotto.</span><span class="sxs-lookup"><span data-stu-id="952d7-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="952d7-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="952d7-126">optAssemProductVersion</span></span>|<span data-ttu-id="952d7-127">Stringa (noto anche come InformationalVersion).</span><span class="sxs-lookup"><span data-stu-id="952d7-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="952d7-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="952d7-128">optAssemCopyright</span></span>|<span data-ttu-id="952d7-129">Stringa - contiene le informazioni sul copyright.</span><span class="sxs-lookup"><span data-stu-id="952d7-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="952d7-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="952d7-130">optAssemTrademark</span></span>|<span data-ttu-id="952d7-131">Stringa - contiene le informazioni sul marchio.</span><span class="sxs-lookup"><span data-stu-id="952d7-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="952d7-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="952d7-132">optAssemKeyFile</span></span>|<span data-ttu-id="952d7-133">String (nome file).</span><span class="sxs-lookup"><span data-stu-id="952d7-133">String (file name).</span></span>|  
|<span data-ttu-id="952d7-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="952d7-134">optAssemKeyName</span></span>|<span data-ttu-id="952d7-135">Stringa (il nome della chiave).</span><span class="sxs-lookup"><span data-stu-id="952d7-135">String (The key name).</span></span>|  
|<span data-ttu-id="952d7-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="952d7-136">optAssemAlgID</span></span>|<span data-ttu-id="952d7-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="952d7-137">ULONG</span></span>|  
|<span data-ttu-id="952d7-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="952d7-138">optAssemFlags</span></span>|<span data-ttu-id="952d7-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="952d7-139">ULONG</span></span>|  
|<span data-ttu-id="952d7-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="952d7-140">optAssemHalfSign</span></span>|<span data-ttu-id="952d7-141">Bool (anche noto come DelaySign).</span><span class="sxs-lookup"><span data-stu-id="952d7-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="952d7-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="952d7-142">optAssemFileVersion</span></span>|<span data-ttu-id="952d7-143">Stringa - codificata come "Revisione", corrisponde a ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="952d7-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="952d7-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="952d7-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="952d7-145">Stringa - codificata come "Revisione".</span><span class="sxs-lookup"><span data-stu-id="952d7-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="952d7-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="952d7-146">optLastAssemOption</span></span>|<span data-ttu-id="952d7-147">Un contatore del numero di elementi.</span><span class="sxs-lookup"><span data-stu-id="952d7-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="952d7-148">Requisiti</span><span class="sxs-lookup"><span data-stu-id="952d7-148">Requirements</span></span>  
 <span data-ttu-id="952d7-149">**Intestazione:** alink.h</span><span class="sxs-lookup"><span data-stu-id="952d7-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="952d7-150">**Libreria**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="952d7-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="952d7-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="952d7-151">See Also</span></span>  
 [<span data-ttu-id="952d7-152">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="952d7-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
