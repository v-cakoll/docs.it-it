---
title: Funzione LoadTypeLibWithResolver
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoadTypeLibWithResolver
api_location: TlbRef.dll
api_type: DLLExport
f1_keywords: LoadTypeLibWithResolver
helpviewer_keywords: LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f069d09f25575c39db097024384ad1bf14eaaf02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="9a9b2-102">Funzione LoadTypeLibWithResolver</span><span class="sxs-lookup"><span data-stu-id="9a9b2-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="9a9b2-103">Carica una libreria dei tipi e utilizza il parametro fornito [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) per risolvere qualsiasi tipo riferimento internamente.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-103">Loads a type library and uses the supplied [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a9b2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a9b2-104">Syntax</span></span>  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a9b2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a9b2-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="9a9b2-106">[in] Percorso del file della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="9a9b2-107">[in] Oggetto [enumerazione REGKIND](https://msdn.microsoft.com/library/windows/desktop/ms221159.aspx) flag che determina come viene registrata la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-107">[in] A [REGKIND enumeration](https://msdn.microsoft.com/library/windows/desktop/ms221159.aspx) flag that controls how the type library is registered.</span></span> <span data-ttu-id="9a9b2-108">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="9a9b2-108">Its possible values are:</span></span>  
  
-   <span data-ttu-id="9a9b2-109">`REGKIND_DEFAULT`: Il comportamento di registrazione predefinito da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
-   <span data-ttu-id="9a9b2-110">`REGKIND_REGISTER`: Registrare la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
-   <span data-ttu-id="9a9b2-111">`REGKIND_NONE`: Non registrare la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="9a9b2-112">[in] Un puntatore all'implementazione del [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9a9b2-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="9a9b2-113">[out] Un riferimento alla libreria dei tipi in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a9b2-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9a9b2-114">Return Value</span></span>  
 <span data-ttu-id="9a9b2-115">Uno dei valori HRESULT elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="9a9b2-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9a9b2-116">Return value</span></span>|<span data-ttu-id="9a9b2-117">Significato</span><span class="sxs-lookup"><span data-stu-id="9a9b2-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="9a9b2-118">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="9a9b2-119">Memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="9a9b2-120">Uno o più dei puntatori non sono validi.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="9a9b2-121">Uno o più argomenti non sono validi.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="9a9b2-122">La funzione non può scrivere nel file.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="9a9b2-123">Impossibile aprire il database di sistema di registrazione.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="9a9b2-124">Non è stato possibile aprire la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="9a9b2-125">Impossibile caricare la libreria dei tipi o DLL.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a9b2-126">Note</span><span class="sxs-lookup"><span data-stu-id="9a9b2-126">Remarks</span></span>  
 <span data-ttu-id="9a9b2-127">Il [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) chiamate di `LoadTypeLibWithResolver` funzione durante il processo di conversione da assembly a libreria.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-127">The [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="9a9b2-128">Questa funzione consente di caricare la libreria dei tipi specificata con un accesso minimo al Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="9a9b2-129">Quindi, la funzione esamina la libreria dei tipi per cui si fa riferimento internamente librerie dei tipi, ognuno dei quali deve essere caricato e aggiunto alla libreria dei tipi padre.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="9a9b2-130">Prima di caricare una libreria dei tipi di riferimento, il percorso del file di riferimento deve essere risolto in un percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="9a9b2-131">Questa operazione viene eseguita tramite il [ResolveTypeLib (metodo)](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) forniti dal [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), che viene passato il `pTlbResolver` parametro.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-131">This is accomplished through the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="9a9b2-132">Quando il percorso completo del file della libreria dei tipi a cui fa riferimento è noto, il `LoadTypeLibWithResolver` funzione carica e aggiunge la libreria dei tipi a cui fa riferimento alla libreria dei tipi padre, la creazione di una libreria dei tipi master combinato.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="9a9b2-133">Dopo che viene risolto e carica tutte le librerie dei tipi a cui fa riferimento internamente, la funzione restituisce un riferimento alla libreria di tipi master risolta nel `pptlib` parametro.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="9a9b2-134">Il `LoadTypeLibWithResolver` funzione viene in genere chiamata dal [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), che fornisce il proprio interno [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementazione nel `pTlbResolver` parametro.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="9a9b2-135">Se si chiama `LoadTypeLibWithResolver` direttamente, è necessario fornire la propria [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementazione.</span><span class="sxs-lookup"><span data-stu-id="9a9b2-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a9b2-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a9b2-136">Requirements</span></span>  
 <span data-ttu-id="9a9b2-137">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a9b2-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a9b2-138">**Intestazione:** TlbRef. H</span><span class="sxs-lookup"><span data-stu-id="9a9b2-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="9a9b2-139">**Libreria:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="9a9b2-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="9a9b2-140">**Versione di .NET framework:** 3.5, 3.0, 2.0</span><span class="sxs-lookup"><span data-stu-id="9a9b2-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a9b2-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a9b2-141">See Also</span></span>  
 [<span data-ttu-id="9a9b2-142">Funzioni di supporto Tlbexp</span><span class="sxs-lookup"><span data-stu-id="9a9b2-142">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 <span data-ttu-id="9a9b2-143">[Funzione LoadTypeLibEx dell'](https://msdn.microsoft.com/library/windows/desktop/ms221249\(v=vs.85\).aspx)</span><span class="sxs-lookup"><span data-stu-id="9a9b2-143">[LoadTypeLibEx Function](https://msdn.microsoft.com/library/windows/desktop/ms221249\(v=vs.85\).aspx)</span></span>
