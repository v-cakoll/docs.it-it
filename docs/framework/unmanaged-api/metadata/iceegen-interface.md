---
title: Interfaccia ICeeGen
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
ms.openlocfilehash: e6cf0aa6f731d0a417e1a2be0ca1d0f8c9299379
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008274"
---
# <a name="iceegen-interface"></a><span data-ttu-id="f3201-102">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="f3201-102">ICeeGen Interface</span></span>
<span data-ttu-id="f3201-103">Fornisce metodi per la compilazione dinamica del codice.</span><span class="sxs-lookup"><span data-stu-id="f3201-103">Provides methods for dynamic code compilation.</span></span>  
  
 <span data-ttu-id="f3201-104">Questa interfaccia è obsoleta e non deve essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="f3201-104">This interface is obsolete and should not be used.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3201-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="f3201-105">Methods</span></span>  
  
|<span data-ttu-id="f3201-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="f3201-106">Method</span></span>|<span data-ttu-id="f3201-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3201-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3201-108">Metodo AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="f3201-108">AddSectionReloc Method</span></span>](iceegen-addsectionreloc-method.md)|<span data-ttu-id="f3201-109">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f3201-109">Obsolete.</span></span> <span data-ttu-id="f3201-110">Aggiunge un'istruzione. reloc alla codebase.</span><span class="sxs-lookup"><span data-stu-id="f3201-110">Adds a .reloc instruction to the code base.</span></span>|  
|[<span data-ttu-id="f3201-111">Metodo AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="f3201-111">AllocateMethodBuffer Method</span></span>](iceegen-allocatemethodbuffer-method.md)|<span data-ttu-id="f3201-112">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f3201-112">Obsolete.</span></span> <span data-ttu-id="f3201-113">Crea un buffer con la dimensione specificata per un metodo e ottiene l'indirizzo virtuale relativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="f3201-113">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>|  
|[<span data-ttu-id="f3201-114">Metodo ComputePointer</span><span class="sxs-lookup"><span data-stu-id="f3201-114">ComputePointer Method</span></span>](iceegen-computepointer-method.md)|<span data-ttu-id="f3201-115">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f3201-115">Obsolete.</span></span> <span data-ttu-id="f3201-116">Determina il buffer per la sezione di codice specificata.</span><span class="sxs-lookup"><span data-stu-id="f3201-116">Determines the buffer for the specified code section.</span></span>|  
|[<span data-ttu-id="f3201-117">Metodo EmitString</span><span class="sxs-lookup"><span data-stu-id="f3201-117">EmitString Method</span></span>](iceegen-emitstring-method.md)|<span data-ttu-id="f3201-118">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f3201-118">Obsolete.</span></span> <span data-ttu-id="f3201-119">Genera la stringa specificata nella codebase.</span><span class="sxs-lookup"><span data-stu-id="f3201-119">Emits the specified string into the code base.</span></span>|  
|[<span data-ttu-id="f3201-120">Metodo GenerateCeeFile</span><span class="sxs-lookup"><span data-stu-id="f3201-120">GenerateCeeFile Method</span></span>](iceegen-generateceefile-method.md)|<span data-ttu-id="f3201-121">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f3201-121">Obsolete.</span></span> <span data-ttu-id="f3201-122">Genera un file di base del codice che contiene la codebase attualmente caricata in questo oggetto `ICeeGen` .</span><span class="sxs-lookup"><span data-stu-id="f3201-122">Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.</span></span>|  
|[<span data-ttu-id="f3201-123">Metodo GenerateCeeMemoryImage</span><span class="sxs-lookup"><span data-stu-id="f3201-123">GenerateCeeMemoryImage Method</span></span>](iceegen-generateceememoryimage-method.md)|<span data-ttu-id="f3201-124">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f3201-124">Obsolete.</span></span> <span data-ttu-id="f3201-125">Genera un'immagine in memoria per la codebase.</span><span class="sxs-lookup"><span data-stu-id="f3201-125">Generates an image in memory for the code base.</span></span>|  
|[<span data-ttu-id="f3201-126">Metodo GetIlSection</span><span class="sxs-lookup"><span data-stu-id="f3201-126">GetIlSection Method</span></span>](iceegen-getilsection-method.md)|<span data-ttu-id="f3201-127">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f3201-127">Obsolete.</span></span> <span data-ttu-id="f3201-128">Ottiene la sezione della base di codice del linguaggio intermedio a cui fa riferimento l'handle specificato.</span><span class="sxs-lookup"><span data-stu-id="f3201-128">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="f3201-129">Metodo GetIMapTokenIface</span><span class="sxs-lookup"><span data-stu-id="f3201-129">GetIMapTokenIface Method</span></span>](iceegen-getimaptokeniface-method.md)|<span data-ttu-id="f3201-130">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f3201-130">Obsolete.</span></span> <span data-ttu-id="f3201-131">Ottiene l'interfaccia a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="f3201-131">Gets the interface referenced by the specified token.</span></span>|  
|[<span data-ttu-id="f3201-132">Metodo GetMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="f3201-132">GetMethodBuffer Method</span></span>](iceegen-getmethodbuffer-method.md)|<span data-ttu-id="f3201-133">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f3201-133">Obsolete.</span></span> <span data-ttu-id="f3201-134">Ottiene un buffer delle dimensioni appropriate per il metodo in corrispondenza dell'indirizzo virtuale relativo specificato.</span><span class="sxs-lookup"><span data-stu-id="f3201-134">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="f3201-135">Metodo GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="f3201-135">GetSectionBlock Method</span></span>](iceegen-getsectionblock-method.md)|<span data-ttu-id="f3201-136">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f3201-136">Obsolete.</span></span> <span data-ttu-id="f3201-137">Ottiene un blocco di sezione della codebase.</span><span class="sxs-lookup"><span data-stu-id="f3201-137">Gets a section block of the code base.</span></span>|  
|[<span data-ttu-id="f3201-138">Metodo GetSectionCreate</span><span class="sxs-lookup"><span data-stu-id="f3201-138">GetSectionCreate Method</span></span>](iceegen-getsectioncreate-method.md)|<span data-ttu-id="f3201-139">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f3201-139">Obsolete.</span></span> <span data-ttu-id="f3201-140">Genera e ottiene una sezione di codice utilizzando il nome e i valori del flag specificati.</span><span class="sxs-lookup"><span data-stu-id="f3201-140">Generates and gets a code section using the specified name and flag values.</span></span>|  
|[<span data-ttu-id="f3201-141">Metodo GetSectionDataLen</span><span class="sxs-lookup"><span data-stu-id="f3201-141">GetSectionDataLen Method</span></span>](iceegen-getsectiondatalen-method.md)|<span data-ttu-id="f3201-142">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f3201-142">Obsolete.</span></span> <span data-ttu-id="f3201-143">Ottiene la lunghezza della sezione specificata.</span><span class="sxs-lookup"><span data-stu-id="f3201-143">Gets the length of the specified section.</span></span>|  
|[<span data-ttu-id="f3201-144">Metodo GetString</span><span class="sxs-lookup"><span data-stu-id="f3201-144">GetString Method</span></span>](iceegen-getstring-method.md)|<span data-ttu-id="f3201-145">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f3201-145">Obsolete.</span></span> <span data-ttu-id="f3201-146">Ottiene la stringa archiviata nell'indirizzo virtuale relativo specificato.</span><span class="sxs-lookup"><span data-stu-id="f3201-146">Gets the string stored at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="f3201-147">Metodo GetStringSection</span><span class="sxs-lookup"><span data-stu-id="f3201-147">GetStringSection Method</span></span>](iceegen-getstringsection-method.md)|<span data-ttu-id="f3201-148">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f3201-148">Obsolete.</span></span> <span data-ttu-id="f3201-149">Ottiene una rappresentazione di stringa della sezione di codice a cui fa riferimento l'handle specificato.</span><span class="sxs-lookup"><span data-stu-id="f3201-149">Gets a string representation of the code section referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="f3201-150">Metodo TruncateSection</span><span class="sxs-lookup"><span data-stu-id="f3201-150">TruncateSection Method</span></span>](iceegen-truncatesection-method.md)|<span data-ttu-id="f3201-151">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f3201-151">Obsolete.</span></span> <span data-ttu-id="f3201-152">Tronca la sezione di codice specificata in base alla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="f3201-152">Truncates the specified code section by the specified length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3201-153">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3201-153">Requirements</span></span>  
 <span data-ttu-id="f3201-154">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3201-154">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3201-155">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f3201-155">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3201-156">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f3201-156">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f3201-157">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3201-157">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3201-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3201-158">See also</span></span>

- [<span data-ttu-id="f3201-159">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="f3201-159">Metadata Interfaces</span></span>](metadata-interfaces.md)
