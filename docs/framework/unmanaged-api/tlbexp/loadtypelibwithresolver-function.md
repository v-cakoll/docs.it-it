---
title: Funzione LoadTypeLibWithResolver
ms.date: 03/30/2017
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c14080e3ac128a6a7fbb48586f59d8a5ea4105f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155662"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="077b7-102">Funzione LoadTypeLibWithResolver</span><span class="sxs-lookup"><span data-stu-id="077b7-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="077b7-103">Carica una libreria dei tipi e Usa il parametro fornito [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) per risolvere eventuali librerie dei tipi riferimento internamente.</span><span class="sxs-lookup"><span data-stu-id="077b7-103">Loads a type library and uses the supplied [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="077b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="077b7-104">Syntax</span></span>  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a><span data-ttu-id="077b7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="077b7-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="077b7-106">[in] Percorso del file della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="077b7-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="077b7-107">[in] Oggetto [enumerazione REGKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) flag che controlla la modalità di registrazione della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="077b7-107">[in] A [REGKIND enumeration](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="077b7-108">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="077b7-108">Its possible values are:</span></span>  
  
-   <span data-ttu-id="077b7-109">`REGKIND_DEFAULT`: Utilizzare il comportamento di registrazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="077b7-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
-   <span data-ttu-id="077b7-110">`REGKIND_REGISTER`: Registrare questa libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="077b7-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
-   <span data-ttu-id="077b7-111">`REGKIND_NONE`: Non registrare questa libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="077b7-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="077b7-112">[in] Un puntatore all'implementazione del [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span><span class="sxs-lookup"><span data-stu-id="077b7-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="077b7-113">[out] Un riferimento alla libreria dei tipi in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="077b7-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="077b7-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="077b7-114">Return Value</span></span>  
 <span data-ttu-id="077b7-115">Uno dei valori di HRESULT elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="077b7-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="077b7-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="077b7-116">Return value</span></span>|<span data-ttu-id="077b7-117">Significato</span><span class="sxs-lookup"><span data-stu-id="077b7-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="077b7-118">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="077b7-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="077b7-119">Memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="077b7-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="077b7-120">Uno o più degli indicatori di misura non sono validi.</span><span class="sxs-lookup"><span data-stu-id="077b7-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="077b7-121">Uno o più argomenti sono validi.</span><span class="sxs-lookup"><span data-stu-id="077b7-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="077b7-122">La funzione non è stato possibile scrivere nel file.</span><span class="sxs-lookup"><span data-stu-id="077b7-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="077b7-123">Non è stato possibile aprire il database di registrazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="077b7-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="077b7-124">Non è stato possibile aprire la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="077b7-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="077b7-125">Non è stato possibile caricare la libreria dei tipi o DLL.</span><span class="sxs-lookup"><span data-stu-id="077b7-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="077b7-126">Note</span><span class="sxs-lookup"><span data-stu-id="077b7-126">Remarks</span></span>  
 <span data-ttu-id="077b7-127">Il [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) chiama il `LoadTypeLibWithResolver` funzione durante il processo di conversione di assembly a libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="077b7-127">The [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="077b7-128">Questa funzione consente di caricare la libreria dei tipi specificata con accesso minimo al Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="077b7-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="077b7-129">La funzione esamina quindi la libreria dei tipi di librerie dei tipi a cui si fa riferimento internamente ognuno dei quali deve essere caricato e aggiunti alla libreria dei tipi padre.</span><span class="sxs-lookup"><span data-stu-id="077b7-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="077b7-130">Prima di caricare una libreria dei tipi riferimento, il percorso del file di riferimento deve essere risolto in un percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="077b7-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="077b7-131">Questa operazione viene eseguita tramite il [ResolveTypeLib (metodo)](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) fornito dal [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), che viene passato il `pTlbResolver` parametro.</span><span class="sxs-lookup"><span data-stu-id="077b7-131">This is accomplished through the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="077b7-132">Quando è noto il percorso completo del file della libreria dei tipi riferimento, il `LoadTypeLibWithResolver` funzione carica e aggiunge la libreria dei tipi di cui si fa riferimento alla libreria dei tipi padre, la creazione di una libreria dei tipi master combinato.</span><span class="sxs-lookup"><span data-stu-id="077b7-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="077b7-133">Dopo che viene risolto e carica tutte le librerie dei tipi riferimento internamente, la funzione restituisce un riferimento alla libreria dei tipi risolto master nel `pptlib` parametro.</span><span class="sxs-lookup"><span data-stu-id="077b7-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="077b7-134">Il `LoadTypeLibWithResolver` funzione viene in genere chiamata dal [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), che fornisce un proprio interni [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementazione nel `pTlbResolver` parametro.</span><span class="sxs-lookup"><span data-stu-id="077b7-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="077b7-135">Se si chiama `LoadTypeLibWithResolver` direttamente, è necessario fornire il proprio [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementazione.</span><span class="sxs-lookup"><span data-stu-id="077b7-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="077b7-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="077b7-136">Requirements</span></span>  
 <span data-ttu-id="077b7-137">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="077b7-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="077b7-138">**Intestazione:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="077b7-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="077b7-139">**Libreria:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="077b7-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="077b7-140">**Versione di .NET framework:** 3.5, 3.0, 2.0</span><span class="sxs-lookup"><span data-stu-id="077b7-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="077b7-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="077b7-141">See also</span></span>

- [<span data-ttu-id="077b7-142">Funzioni di supporto Tlbexp</span><span class="sxs-lookup"><span data-stu-id="077b7-142">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="077b7-143">Funzione LoadTypeLibEx dell'</span><span class="sxs-lookup"><span data-stu-id="077b7-143">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
