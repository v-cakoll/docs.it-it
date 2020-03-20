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
ms.openlocfilehash: c0f81e3767d4ea3bc336203fbe8c914b4e2bd07b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177796"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="2eabc-102">Metodo IMetaDataAssemblyImport::FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="2eabc-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="2eabc-103">Ottiene una matrice di `szAssemblyName` assembly con il parametro specificato, utilizzando le regole standard utilizzate da Common Language Runtime (CLR) per la risoluzione dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="2eabc-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2eabc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2eabc-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2eabc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2eabc-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="2eabc-106">[in] Directory radice in cui cercare l'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="2eabc-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="2eabc-107">Se questo valore `null`è `FindAssembliesByName` impostato su , cercherà l'assembly solo nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="2eabc-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="2eabc-108">[in] Un elenco di sottodirectory delimitate da punti e virgola (ad esempio, "bin;bin2"), nella directory radice, in cui cercare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="2eabc-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="2eabc-109">Queste directory vengono esaminate in aggiunta a quelle specificate nelle regole di sondaggio predefinite.</span><span class="sxs-lookup"><span data-stu-id="2eabc-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="2eabc-110">[in] Nome dell'assembly da trovare.</span><span class="sxs-lookup"><span data-stu-id="2eabc-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="2eabc-111">Il formato di questa stringa è definito <xref:System.Reflection.AssemblyName>nella pagina di riferimento della classe per .</span><span class="sxs-lookup"><span data-stu-id="2eabc-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="2eabc-112">[in] Matrice di tipo [IUnknown](/cpp/atl/iunknown) in `IMetadataAssemblyImport` cui inserire i puntatori a interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2eabc-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2eabc-113">[fuori] Numero massimo di puntatori a interfaccia `ppIUnk`che è possibile inserire in .</span><span class="sxs-lookup"><span data-stu-id="2eabc-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="2eabc-114">[fuori] Numero di puntatori a interfaccia restituiti.</span><span class="sxs-lookup"><span data-stu-id="2eabc-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="2eabc-115">Ovvero, il numero di puntatori `ppIUnk`a interfaccia effettivamente inseriti in .</span><span class="sxs-lookup"><span data-stu-id="2eabc-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2eabc-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2eabc-116">Return Value</span></span>  
  
|<span data-ttu-id="2eabc-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2eabc-117">HRESULT</span></span>|<span data-ttu-id="2eabc-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2eabc-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2eabc-119">`FindAssembliesByName`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="2eabc-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2eabc-120">Non ci sono assembly.</span><span class="sxs-lookup"><span data-stu-id="2eabc-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2eabc-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2eabc-121">Remarks</span></span>  
 <span data-ttu-id="2eabc-122">Dato il nome `FindAssembliesByName` di un assembly, il metodo trova l'assembly seguendo le regole standard per la risoluzione dei riferimenti all'assembly.</span><span class="sxs-lookup"><span data-stu-id="2eabc-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="2eabc-123">Per ulteriori informazioni, vedere [Come il runtime individua gli assembly.](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) `FindAssembliesByName` consente al chiamante di configurare vari aspetti del contesto del sistema di risoluzione degli assembly, ad esempio la base dell'applicazione e il percorso di ricerca privato.</span><span class="sxs-lookup"><span data-stu-id="2eabc-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="2eabc-124">Il `FindAssembliesByName` metodo richiede che CLR venga inizializzato nel processo per richiamare la logica di risoluzione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2eabc-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="2eabc-125">Pertanto, è necessario chiamare [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) `FindAssembliesByName`(passaggio COINITEE_DEFAULT) prima di chiamare , quindi seguire una chiamata a [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span><span class="sxs-lookup"><span data-stu-id="2eabc-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="2eabc-126">`FindAssembliesByName`restituisce un puntatore [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) al file contenente il manifesto dell'assembly per il nome dell'assembly passato.</span><span class="sxs-lookup"><span data-stu-id="2eabc-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="2eabc-127">Se il nome dell'assembly specificato non è completamente specificato (ad esempio, se non include una versione), è possibile che vengano restituiti più assembly.</span><span class="sxs-lookup"><span data-stu-id="2eabc-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="2eabc-128">`FindAssembliesByName`viene in genere utilizzato da un compilatore che tenta di trovare un assembly di riferimento in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="2eabc-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2eabc-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2eabc-129">Requirements</span></span>  
 <span data-ttu-id="2eabc-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2eabc-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2eabc-131">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2eabc-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2eabc-132">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2eabc-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2eabc-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2eabc-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eabc-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2eabc-134">See also</span></span>

- [<span data-ttu-id="2eabc-135">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="2eabc-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="2eabc-136">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="2eabc-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
