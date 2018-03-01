---
title: Metodo IMetaDataAssemblyImport::FindAssembliesByName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d6518fdcf1bef8eaea74818f69f46bb6df26e31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="32f4d-102">Metodo IMetaDataAssemblyImport::FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="32f4d-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="32f4d-103">Ottiene una matrice di assembly con l'oggetto specificato `szAssemblyName` parametro, utilizzando le regole standard utilizzate da common language runtime (CLR) per la risoluzione dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="32f4d-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32f4d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="32f4d-104">Syntax</span></span>  
  
```  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,   
    [in]  LPCWSTR     szPrivateBin,   
    [in]  LPCWSTR     szAssemblyName,   
    [out] IUnknown    *ppIUnk[],   
    [in]  ULONG       cMax,   
    [out] ULONG       *pcAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32f4d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="32f4d-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="32f4d-106">[in] La directory radice in cui eseguire la ricerca per l'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="32f4d-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="32f4d-107">Se questo valore è impostato su `null`, `FindAssembliesByName` verranno ricercati solo nella global assembly cache l'assembly.</span><span class="sxs-lookup"><span data-stu-id="32f4d-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="32f4d-108">[in] Elenco delimitato da punto e virgola sottodirectory (ad esempio, "bin; bin2"), la directory radice, in cui eseguire la ricerca dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="32f4d-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="32f4d-109">Queste directory subiscono oltre a quelli specificati nelle regole di ricerca predefinite.</span><span class="sxs-lookup"><span data-stu-id="32f4d-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="32f4d-110">[in] Il nome dell'assembly da trovare.</span><span class="sxs-lookup"><span data-stu-id="32f4d-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="32f4d-111">Il formato di questa stringa è definito nella pagina di riferimento di classe per <xref:System.Reflection.AssemblyName>.</span><span class="sxs-lookup"><span data-stu-id="32f4d-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="32f4d-112">[in] Matrice di tipo <<!--zzxref:IUnknown --> `IUnknown`> in cui inserire il `IMetadataAssemblyImport` i puntatori a interfaccia.</span><span class="sxs-lookup"><span data-stu-id="32f4d-112">[in] An array of type <<!--zzxref:IUnknown --> `IUnknown`> in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="32f4d-113">[out] Il numero massimo di puntatori a interfaccia che può essere inserita in `ppIUnk`.</span><span class="sxs-lookup"><span data-stu-id="32f4d-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="32f4d-114">[out] Il numero di puntatori a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="32f4d-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="32f4d-115">Vale a dire il numero di puntatori a interfaccia effettivamente inseriti in `ppIUnk`.</span><span class="sxs-lookup"><span data-stu-id="32f4d-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32f4d-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="32f4d-116">Return Value</span></span>  
  
|<span data-ttu-id="32f4d-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32f4d-117">HRESULT</span></span>|<span data-ttu-id="32f4d-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32f4d-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="32f4d-119">`FindAssembliesByName`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="32f4d-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="32f4d-120">Non esistono alcun assembly.</span><span class="sxs-lookup"><span data-stu-id="32f4d-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32f4d-121">Note</span><span class="sxs-lookup"><span data-stu-id="32f4d-121">Remarks</span></span>  
 <span data-ttu-id="32f4d-122">Dato un nome di assembly, il `FindAssembliesByName` metodo individua l'assembly seguendo le regole per la risoluzione di riferimenti ad assembly standard.</span><span class="sxs-lookup"><span data-stu-id="32f4d-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="32f4d-123">(Per ulteriori informazioni, vedere [come il Runtime individua gli assembly](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` consente al chiamante di configurare diversi aspetti del contesto di sistema di risoluzione assembly, ad esempio il percorso di ricerca privato e base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="32f4d-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="32f4d-124">Il `FindAssembliesByName` metodo richiede l'inizializzazione del processo per richiamare la logica di risoluzione assembly CLR.</span><span class="sxs-lookup"><span data-stu-id="32f4d-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="32f4d-125">Pertanto, è necessario chiamare [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passando COINITEE_DEFAULT) prima di chiamare `FindAssembliesByName`, quindi seguire con una chiamata a [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span><span class="sxs-lookup"><span data-stu-id="32f4d-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="32f4d-126">`FindAssembliesByName`Restituisce un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) puntatore del file contenente il manifesto dell'assembly per il nome dell'assembly che viene passato.</span><span class="sxs-lookup"><span data-stu-id="32f4d-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="32f4d-127">Se il nome di assembly specificato non è completamente specificato (ad esempio, se non include una versione), che vengano restituiti più assembly.</span><span class="sxs-lookup"><span data-stu-id="32f4d-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="32f4d-128">`FindAssembliesByName`in genere viene utilizzato da un compilatore che tenta di trovare un assembly di riferimento in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="32f4d-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32f4d-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="32f4d-129">Requirements</span></span>  
 <span data-ttu-id="32f4d-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32f4d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32f4d-131">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="32f4d-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="32f4d-132">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="32f4d-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="32f4d-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32f4d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32f4d-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32f4d-134">See Also</span></span>  
 [<span data-ttu-id="32f4d-135">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="32f4d-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="32f4d-136">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="32f4d-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
