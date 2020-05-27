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
ms.openlocfilehash: 05902436c09d082f90af01f48c7e918650317ce7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009418"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="0284f-102">Metodo IMetaDataAssemblyImport::FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="0284f-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="0284f-103">Ottiene una matrice di assembly con il `szAssemblyName` parametro specificato, utilizzando le regole standard utilizzate dal Common Language Runtime (CLR) per la risoluzione dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="0284f-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0284f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0284f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="0284f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0284f-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="0284f-106">in Directory radice in cui cercare l'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="0284f-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="0284f-107">Se questo valore è impostato su `null` , `FindAssembliesByName` verrà cercato solo nell'global assembly cache per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="0284f-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="0284f-108">in Elenco di sottodirectory delimitate da punto e virgola, ad esempio "bin; BIN2", nella directory radice in cui cercare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="0284f-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="0284f-109">Queste directory vengono verificate in aggiunta a quelle specificate nelle regole di probe predefinite.</span><span class="sxs-lookup"><span data-stu-id="0284f-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="0284f-110">in Nome dell'assembly da trovare.</span><span class="sxs-lookup"><span data-stu-id="0284f-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="0284f-111">Il formato di questa stringa è definito nella pagina di riferimento della classe per <xref:System.Reflection.AssemblyName> .</span><span class="sxs-lookup"><span data-stu-id="0284f-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="0284f-112">in Matrice di tipo [IUnknown](/cpp/atl/iunknown) in cui inserire i `IMetadataAssemblyImport` puntatori all'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="0284f-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0284f-113">out Numero massimo di puntatori di interfaccia che possono essere inseriti in `ppIUnk` .</span><span class="sxs-lookup"><span data-stu-id="0284f-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="0284f-114">out Numero di puntatori a interfaccia restituiti.</span><span class="sxs-lookup"><span data-stu-id="0284f-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="0284f-115">Ovvero il numero di puntatori di interfaccia effettivamente posizionati in `ppIUnk` .</span><span class="sxs-lookup"><span data-stu-id="0284f-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0284f-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0284f-116">Return Value</span></span>  
  
|<span data-ttu-id="0284f-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0284f-117">HRESULT</span></span>|<span data-ttu-id="0284f-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0284f-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0284f-119">`FindAssembliesByName`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="0284f-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0284f-120">Nessun assembly.</span><span class="sxs-lookup"><span data-stu-id="0284f-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0284f-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="0284f-121">Remarks</span></span>  
 <span data-ttu-id="0284f-122">Dato il nome di un assembly, il `FindAssembliesByName` metodo trova l'assembly seguendo le regole standard per la risoluzione dei riferimenti ad assembly.</span><span class="sxs-lookup"><span data-stu-id="0284f-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="0284f-123">Per ulteriori informazioni, vedere [come il runtime individua gli assembly](../../deployment/how-the-runtime-locates-assemblies.md). `FindAssembliesByName`consente al chiamante di configurare vari aspetti del contesto del resolver dell'assembly, ad esempio il percorso di ricerca privato e di base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0284f-123">(For more information, see [How the Runtime Locates Assemblies](../../deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="0284f-124">Il `FindAssembliesByName` metodo richiede l'inizializzazione di CLR nel processo per richiamare la logica di risoluzione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0284f-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="0284f-125">Pertanto, è necessario chiamare [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passando COINITEE_DEFAULT) prima di chiamare `FindAssembliesByName` e quindi seguire con una chiamata a [CoUninitializeCor](../hosting/couninitializecor-function.md).</span><span class="sxs-lookup"><span data-stu-id="0284f-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="0284f-126">`FindAssembliesByName`Restituisce un puntatore [IMetaDataImport](imetadataimport-interface.md) al file contenente il manifesto dell'assembly per il nome dell'assembly passato.</span><span class="sxs-lookup"><span data-stu-id="0284f-126">`FindAssembliesByName` returns an [IMetaDataImport](imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="0284f-127">Se il nome dell'assembly specificato non è completamente specificato (ad esempio, se non include una versione), potrebbero essere restituiti più assembly.</span><span class="sxs-lookup"><span data-stu-id="0284f-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="0284f-128">`FindAssembliesByName`viene comunemente usato da un compilatore che tenta di trovare un assembly a cui si fa riferimento in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="0284f-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0284f-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0284f-129">Requirements</span></span>  
 <span data-ttu-id="0284f-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0284f-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0284f-131">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0284f-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0284f-132">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0284f-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0284f-133">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0284f-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0284f-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0284f-134">See also</span></span>

- [<span data-ttu-id="0284f-135">Modalità di individuazione degli assembly da parte del runtime</span><span class="sxs-lookup"><span data-stu-id="0284f-135">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="0284f-136">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="0284f-136">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
