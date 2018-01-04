---
title: Interfaccia ICeeGen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen
helpviewer_keywords: ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73af58ac55fd22e5b4f19f715cb0b1a137a640a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iceegen-interface"></a><span data-ttu-id="3e25a-102">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="3e25a-102">ICeeGen Interface</span></span>
<span data-ttu-id="3e25a-103">Fornisce metodi per la compilazione dinamica del codice.</span><span class="sxs-lookup"><span data-stu-id="3e25a-103">Provides methods for dynamic code compilation.</span></span>  
  
 <span data-ttu-id="3e25a-104">Questa interfaccia è obsoleta e non deve essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="3e25a-104">This interface is obsolete and should not be used.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e25a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3e25a-105">Methods</span></span>  
  
|<span data-ttu-id="3e25a-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="3e25a-106">Method</span></span>|<span data-ttu-id="3e25a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e25a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e25a-108">Metodo AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="3e25a-108">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|<span data-ttu-id="3e25a-109">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3e25a-109">Obsolete.</span></span> <span data-ttu-id="3e25a-110">Aggiunge un'istruzione. reloc alla base di codice.</span><span class="sxs-lookup"><span data-stu-id="3e25a-110">Adds a .reloc instruction to the code base.</span></span>|  
|[<span data-ttu-id="3e25a-111">Metodo AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="3e25a-111">AllocateMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|<span data-ttu-id="3e25a-112">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3e25a-112">Obsolete.</span></span> <span data-ttu-id="3e25a-113">Crea un buffer della dimensione specificata per un metodo e ottiene l'indirizzo virtuale relativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="3e25a-113">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>|  
|[<span data-ttu-id="3e25a-114">Metodo ComputePointer</span><span class="sxs-lookup"><span data-stu-id="3e25a-114">ComputePointer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|<span data-ttu-id="3e25a-115">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3e25a-115">Obsolete.</span></span> <span data-ttu-id="3e25a-116">Determina il buffer per la sezione di codice specificato.</span><span class="sxs-lookup"><span data-stu-id="3e25a-116">Determines the buffer for the specified code section.</span></span>|  
|[<span data-ttu-id="3e25a-117">Metodo EmitString</span><span class="sxs-lookup"><span data-stu-id="3e25a-117">EmitString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|<span data-ttu-id="3e25a-118">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3e25a-118">Obsolete.</span></span> <span data-ttu-id="3e25a-119">Genera la stringa specificata nella codebase.</span><span class="sxs-lookup"><span data-stu-id="3e25a-119">Emits the specified string into the code base.</span></span>|  
|[<span data-ttu-id="3e25a-120">Metodo GenerateCeeFile</span><span class="sxs-lookup"><span data-stu-id="3e25a-120">GenerateCeeFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|<span data-ttu-id="3e25a-121">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3e25a-121">Obsolete.</span></span> <span data-ttu-id="3e25a-122">Genera un file di base di codice che contiene il codice base attualmente caricato in `ICeeGen`.</span><span class="sxs-lookup"><span data-stu-id="3e25a-122">Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.</span></span>|  
|[<span data-ttu-id="3e25a-123">Metodo GenerateCeeMemoryImage</span><span class="sxs-lookup"><span data-stu-id="3e25a-123">GenerateCeeMemoryImage Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|<span data-ttu-id="3e25a-124">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3e25a-124">Obsolete.</span></span> <span data-ttu-id="3e25a-125">Genera un'immagine in memoria per la base di codice.</span><span class="sxs-lookup"><span data-stu-id="3e25a-125">Generates an image in memory for the code base.</span></span>|  
|[<span data-ttu-id="3e25a-126">Metodo GetIlSection</span><span class="sxs-lookup"><span data-stu-id="3e25a-126">GetIlSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|<span data-ttu-id="3e25a-127">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3e25a-127">Obsolete.</span></span> <span data-ttu-id="3e25a-128">Ottiene la sezione di codice Microsoft intermediate language base a cui fa riferimento l'handle specificato.</span><span class="sxs-lookup"><span data-stu-id="3e25a-128">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="3e25a-129">Metodo GetIMapTokenIface</span><span class="sxs-lookup"><span data-stu-id="3e25a-129">GetIMapTokenIface Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|<span data-ttu-id="3e25a-130">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3e25a-130">Obsolete.</span></span> <span data-ttu-id="3e25a-131">Ottiene l'interfaccia a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="3e25a-131">Gets the interface referenced by the specified token.</span></span>|  
|[<span data-ttu-id="3e25a-132">Metodo GetMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="3e25a-132">GetMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|<span data-ttu-id="3e25a-133">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3e25a-133">Obsolete.</span></span> <span data-ttu-id="3e25a-134">Ottiene un buffer di dimensioni appropriate per il metodo all'indirizzo virtuale relativo specificato.</span><span class="sxs-lookup"><span data-stu-id="3e25a-134">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="3e25a-135">Metodo GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="3e25a-135">GetSectionBlock Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|<span data-ttu-id="3e25a-136">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3e25a-136">Obsolete.</span></span> <span data-ttu-id="3e25a-137">Ottiene un blocco di sezione di base di codice.</span><span class="sxs-lookup"><span data-stu-id="3e25a-137">Gets a section block of the code base.</span></span>|  
|[<span data-ttu-id="3e25a-138">Metodo GetSectionCreate</span><span class="sxs-lookup"><span data-stu-id="3e25a-138">GetSectionCreate Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|<span data-ttu-id="3e25a-139">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3e25a-139">Obsolete.</span></span> <span data-ttu-id="3e25a-140">Genera l'errore e ottiene una sezione di codice utilizzando il nome specificato e i valori di flag.</span><span class="sxs-lookup"><span data-stu-id="3e25a-140">Generates and gets a code section using the specified name and flag values.</span></span>|  
|[<span data-ttu-id="3e25a-141">Metodo GetSectionDataLen</span><span class="sxs-lookup"><span data-stu-id="3e25a-141">GetSectionDataLen Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|<span data-ttu-id="3e25a-142">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3e25a-142">Obsolete.</span></span> <span data-ttu-id="3e25a-143">Ottiene la lunghezza della sezione specificata.</span><span class="sxs-lookup"><span data-stu-id="3e25a-143">Gets the length of the specified section.</span></span>|  
|[<span data-ttu-id="3e25a-144">Metodo GetString</span><span class="sxs-lookup"><span data-stu-id="3e25a-144">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|<span data-ttu-id="3e25a-145">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3e25a-145">Obsolete.</span></span> <span data-ttu-id="3e25a-146">Ottiene la stringa archiviata nell'indirizzo virtuale relativo specificato.</span><span class="sxs-lookup"><span data-stu-id="3e25a-146">Gets the string stored at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="3e25a-147">Metodo GetStringSection</span><span class="sxs-lookup"><span data-stu-id="3e25a-147">GetStringSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|<span data-ttu-id="3e25a-148">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3e25a-148">Obsolete.</span></span> <span data-ttu-id="3e25a-149">Ottiene una rappresentazione di stringa della sezione di codice a cui fa riferimento l'handle specificato.</span><span class="sxs-lookup"><span data-stu-id="3e25a-149">Gets a string representation of the code section referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="3e25a-150">Metodo TruncateSection</span><span class="sxs-lookup"><span data-stu-id="3e25a-150">TruncateSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|<span data-ttu-id="3e25a-151">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3e25a-151">Obsolete.</span></span> <span data-ttu-id="3e25a-152">Tronca la sezione di codice specificati dalla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="3e25a-152">Truncates the specified code section by the specified length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3e25a-153">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e25a-153">Requirements</span></span>  
 <span data-ttu-id="3e25a-154">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e25a-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e25a-155">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3e25a-155">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e25a-156">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e25a-156">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3e25a-157">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e25a-157">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e25a-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e25a-158">See Also</span></span>  
 [<span data-ttu-id="3e25a-159">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="3e25a-159">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
