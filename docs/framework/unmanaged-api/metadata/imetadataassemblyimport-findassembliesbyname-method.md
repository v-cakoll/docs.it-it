---
title: Metodo IMetaDataAssemblyImport::FindAssembliesByName
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 315d9aa6f7db51342e71ba3f8fcdc091f7707743
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777975"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="6fff1-102">Metodo IMetaDataAssemblyImport::FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="6fff1-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="6fff1-103">Ottiene una matrice di assembly specificato `szAssemblyName` parametro, usando le regole standard utilizzate da common language runtime (CLR) per la risoluzione dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="6fff1-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fff1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6fff1-104">Syntax</span></span>  
  
```cpp  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,   
    [in]  LPCWSTR     szPrivateBin,   
    [in]  LPCWSTR     szAssemblyName,   
    [out] IUnknown    *ppIUnk[],   
    [in]  ULONG       cMax,   
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fff1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6fff1-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="6fff1-106">[in] Directory radice in cui cercare l'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="6fff1-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="6fff1-107">Se questo valore è impostato su `null`, `FindAssembliesByName` Cerca solo nella global assembly cache l'assembly.</span><span class="sxs-lookup"><span data-stu-id="6fff1-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="6fff1-108">[in] Un elenco delle sottodirectory delimitato da punto e virgola (, ad esempio, "bin; bin2"), sotto la directory radice, in cui eseguire la ricerca dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="6fff1-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="6fff1-109">Queste directory subiscono oltre a quelli specificati nell'impostazione predefinita le regole di individuazione tramite probe.</span><span class="sxs-lookup"><span data-stu-id="6fff1-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="6fff1-110">[in] Il nome dell'assembly da trovare.</span><span class="sxs-lookup"><span data-stu-id="6fff1-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="6fff1-111">Il formato di questa stringa è definito nella pagina di riferimento di classe per <xref:System.Reflection.AssemblyName>.</span><span class="sxs-lookup"><span data-stu-id="6fff1-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="6fff1-112">[in] Matrice di tipo [IUnknown](/cpp/atl/iunknown) in cui inserire il `IMetadataAssemblyImport` puntatori a interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6fff1-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6fff1-113">[out] Il numero massimo di puntatori a interfaccia che può essere inserito in `ppIUnk`.</span><span class="sxs-lookup"><span data-stu-id="6fff1-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="6fff1-114">[out] Il numero dei puntatori a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="6fff1-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="6fff1-115">Vale a dire il numero dei puntatori a interfaccia effettivamente posizionati `ppIUnk`.</span><span class="sxs-lookup"><span data-stu-id="6fff1-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6fff1-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6fff1-116">Return Value</span></span>  
  
|<span data-ttu-id="6fff1-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6fff1-117">HRESULT</span></span>|<span data-ttu-id="6fff1-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6fff1-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6fff1-119">`FindAssembliesByName` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="6fff1-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6fff1-120">Non esistono alcun assembly.</span><span class="sxs-lookup"><span data-stu-id="6fff1-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fff1-121">Note</span><span class="sxs-lookup"><span data-stu-id="6fff1-121">Remarks</span></span>  
 <span data-ttu-id="6fff1-122">Dato un nome dell'assembly, il `FindAssembliesByName` metodo trova l'assembly, seguendo le regole standard per la risoluzione dei riferimenti ad assembly.</span><span class="sxs-lookup"><span data-stu-id="6fff1-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="6fff1-123">(Per altre informazioni, vedere [modo in cui il Runtime individua gli assembly](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` consente al chiamante configurare vari aspetti del contesto del resolver di assembly, ad esempio il percorso di ricerca di base e privata dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6fff1-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="6fff1-124">Il `FindAssembliesByName` metodo richiesto a CLR di inizializzare il processo per richiamare la logica di risoluzione di assembly.</span><span class="sxs-lookup"><span data-stu-id="6fff1-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="6fff1-125">Pertanto, è necessario chiamare [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passando COINITEE_DEFAULT) prima di chiamare `FindAssembliesByName`, quindi seguire con una chiamata al [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span><span class="sxs-lookup"><span data-stu-id="6fff1-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="6fff1-126">`FindAssembliesByName` Restituisce un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) puntatore del file contenente il manifesto dell'assembly per il nome dell'assembly che viene passato.</span><span class="sxs-lookup"><span data-stu-id="6fff1-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="6fff1-127">Se il nome dell'assembly specificata non è completamente specificato (ad esempio, se non sono incluse una versione), potrebbe essere restituito più assembly.</span><span class="sxs-lookup"><span data-stu-id="6fff1-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="6fff1-128">`FindAssembliesByName` viene utilizzata solitamente da un compilatore che tenta di trovare un assembly di riferimento in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6fff1-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fff1-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6fff1-129">Requirements</span></span>  
 <span data-ttu-id="6fff1-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fff1-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fff1-131">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6fff1-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6fff1-132">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6fff1-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6fff1-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fff1-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fff1-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fff1-134">See also</span></span>

- [<span data-ttu-id="6fff1-135">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="6fff1-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="6fff1-136">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="6fff1-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
