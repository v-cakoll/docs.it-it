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
ms.openlocfilehash: b78789344050fd5e1cb0ee3492bf330fbf92bc88
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798926"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="4bef2-102">Funzione LoadTypeLibWithResolver</span><span class="sxs-lookup"><span data-stu-id="4bef2-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="4bef2-103">Carica una libreria dei tipi e utilizza l' [interfaccia ITypeLibResolver](itypelibresolver-interface.md) fornita per risolvere le librerie dei tipi a cui si fa riferimento internamente.</span><span class="sxs-lookup"><span data-stu-id="4bef2-103">Loads a type library and uses the supplied [ITypeLibResolver interface](itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bef2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4bef2-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bef2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4bef2-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="4bef2-106">in Percorso del file della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="4bef2-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="4bef2-107">in Flag di [enumerazione REGKIND](https://docs.microsoft.com/windows/win32/api/oleauto/ne-oleauto-regkind) che controlla la modalità di registrazione della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="4bef2-107">[in] A [REGKIND enumeration](https://docs.microsoft.com/windows/win32/api/oleauto/ne-oleauto-regkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="4bef2-108">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="4bef2-108">Its possible values are:</span></span>  
  
- <span data-ttu-id="4bef2-109">`REGKIND_DEFAULT`: Usare il comportamento di registrazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="4bef2-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
- <span data-ttu-id="4bef2-110">`REGKIND_REGISTER`: Registrare questa libreria di tipi.</span><span class="sxs-lookup"><span data-stu-id="4bef2-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
- <span data-ttu-id="4bef2-111">`REGKIND_NONE`: Non registrare questa libreria di tipi.</span><span class="sxs-lookup"><span data-stu-id="4bef2-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="4bef2-112">in Puntatore all'implementazione dell' [interfaccia ITypeLibResolver](itypelibresolver-interface.md).</span><span class="sxs-lookup"><span data-stu-id="4bef2-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="4bef2-113">out Riferimento alla libreria dei tipi che viene caricata.</span><span class="sxs-lookup"><span data-stu-id="4bef2-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4bef2-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4bef2-114">Return Value</span></span>  
 <span data-ttu-id="4bef2-115">Uno dei valori HRESULT elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4bef2-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="4bef2-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4bef2-116">Return value</span></span>|<span data-ttu-id="4bef2-117">Significato</span><span class="sxs-lookup"><span data-stu-id="4bef2-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="4bef2-118">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="4bef2-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="4bef2-119">Memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="4bef2-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="4bef2-120">Uno o più puntatori non sono validi.</span><span class="sxs-lookup"><span data-stu-id="4bef2-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="4bef2-121">Uno o più argomenti non sono validi.</span><span class="sxs-lookup"><span data-stu-id="4bef2-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="4bef2-122">La funzione non è in grado di scrivere nel file.</span><span class="sxs-lookup"><span data-stu-id="4bef2-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="4bef2-123">Non è stato possibile aprire il database di registrazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="4bef2-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="4bef2-124">Non è stato possibile aprire la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="4bef2-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="4bef2-125">Non è stato possibile caricare la libreria dei tipi o la DLL.</span><span class="sxs-lookup"><span data-stu-id="4bef2-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bef2-126">Note</span><span class="sxs-lookup"><span data-stu-id="4bef2-126">Remarks</span></span>  
 <span data-ttu-id="4bef2-127">[Tlbexp. exe (](../../tools/tlbexp-exe-type-library-exporter.md) utilità di esportazione della libreria dei tipi) `LoadTypeLibWithResolver` chiama la funzione durante il processo di conversione da assembly a libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="4bef2-127">The [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="4bef2-128">Questa funzione carica la libreria dei tipi specificata con accesso minimo al registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="4bef2-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="4bef2-129">La funzione esamina quindi la libreria dei tipi per le librerie dei tipi a cui si fa riferimento internamente, ciascuna delle quali deve essere caricata e aggiunta alla libreria dei tipi padre.</span><span class="sxs-lookup"><span data-stu-id="4bef2-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="4bef2-130">Prima di poter caricare una libreria dei tipi a cui viene fatto riferimento, il percorso del file di riferimento deve essere risolto in un percorso file completo.</span><span class="sxs-lookup"><span data-stu-id="4bef2-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="4bef2-131">Questa operazione viene eseguita tramite il [metodo ResolveTypeLib](resolvetypelib-method.md) fornito dall' [interfaccia ITypeLibResolver](itypelibresolver-interface.md), che viene `pTlbResolver` passata nel parametro.</span><span class="sxs-lookup"><span data-stu-id="4bef2-131">This is accomplished through the [ResolveTypeLib method](resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="4bef2-132">Quando è noto il percorso completo del file della libreria dei tipi a cui si `LoadTypeLibWithResolver` fa riferimento, la funzione carica e aggiunge la libreria dei tipi a cui si fa riferimento nella libreria dei tipi padre, creando una libreria dei tipi master combinata.</span><span class="sxs-lookup"><span data-stu-id="4bef2-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="4bef2-133">Dopo che la funzione risolve e carica tutte le librerie dei tipi a cui si fa riferimento internamente, restituisce un riferimento alla libreria dei tipi `pptlib` risolta master nel parametro.</span><span class="sxs-lookup"><span data-stu-id="4bef2-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="4bef2-134">La `LoadTypeLibWithResolver` funzione viene in genere chiamata da [Tlbexp. exe (utilità di esportazione della libreria dei tipi)](../../tools/tlbexp-exe-type-library-exporter.md), che fornisce un'implementazione dell' `pTlbResolver` [interfaccia ITypeLibResolver](itypelibresolver-interface.md) interna nel parametro.</span><span class="sxs-lookup"><span data-stu-id="4bef2-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="4bef2-135">Se si chiama `LoadTypeLibWithResolver` direttamente, è necessario fornire un'implementazione dell' [interfaccia ITypeLibResolver](itypelibresolver-interface.md) personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4bef2-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bef2-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4bef2-136">Requirements</span></span>  
 <span data-ttu-id="4bef2-137">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bef2-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bef2-138">**Intestazione:** TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="4bef2-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="4bef2-139">**Libreria** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="4bef2-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="4bef2-140">**Versione .NET Framework:** 3,5, 3,0, 2,0</span><span class="sxs-lookup"><span data-stu-id="4bef2-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bef2-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bef2-141">See also</span></span>

- [<span data-ttu-id="4bef2-142">Funzioni di supporto Tlbexp</span><span class="sxs-lookup"><span data-stu-id="4bef2-142">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="4bef2-143">LoadTypeLibEx (funzione)</span><span class="sxs-lookup"><span data-stu-id="4bef2-143">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
