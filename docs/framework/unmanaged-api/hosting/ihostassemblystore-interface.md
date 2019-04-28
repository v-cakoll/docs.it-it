---
title: Interfaccia IHostAssemblyStore
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4067c1fbcf99c903c892eaec58262d95569114b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930039"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="763a0-102">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="763a0-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="763a0-103">Fornisce metodi che consentono a un host per il caricamento degli assembly e moduli indipendentemente da common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="763a0-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="763a0-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="763a0-104">Methods</span></span>  
  
|<span data-ttu-id="763a0-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="763a0-105">Method</span></span>|<span data-ttu-id="763a0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="763a0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="763a0-107">Metodo ProvideAssembly</span><span class="sxs-lookup"><span data-stu-id="763a0-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="763a0-108">Ottiene un riferimento a un assembly che non fa riferimento il [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) restituiti da una chiamata a [IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="763a0-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="763a0-109">Metodo ProvideModule</span><span class="sxs-lookup"><span data-stu-id="763a0-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="763a0-110">Risolve un modulo all'interno di un assembly o un file di risorse (non incorporato) collegati.</span><span class="sxs-lookup"><span data-stu-id="763a0-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="763a0-111">Note</span><span class="sxs-lookup"><span data-stu-id="763a0-111">Remarks</span></span>  
 <span data-ttu-id="763a0-112">`IHostAssemblyStore` fornisce un modo per un host caricare gli assembly in modo efficiente in base all'identità dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="763a0-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="763a0-113">L'host carica gli assembly, restituendo `IStream` istanze che puntano direttamente i byte.</span><span class="sxs-lookup"><span data-stu-id="763a0-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="763a0-114">Il CLR determina se un host è implementata `IHostAssemblyStore` chiamando `IHostAssemblyManager::GetNonHostAssemblyStores` al momento dell'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="763a0-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="763a0-115">Ciò consente all'host, ad esempio, per controllare l'associazione di assembly dell'utente, ma affidarsi al runtime di eseguire l'associazione agli assembly .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="763a0-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="763a0-116">Fornendo un'implementazione di `IHostAssemblyStore`, l'host specifica l'intento di risolvere tutti gli assembly che non fa riferimento il `ICLRAssemblyReferenceList` restituiti da `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="763a0-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="763a0-117">.NET Framework versione 2.0 non fornisce un modo per caricare l'immagine nativa di un assembly, l'host fornito dal [generatore di immagini Native (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utilità.</span><span class="sxs-lookup"><span data-stu-id="763a0-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="763a0-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="763a0-118">Requirements</span></span>  
 <span data-ttu-id="763a0-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="763a0-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="763a0-120">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="763a0-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="763a0-121">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="763a0-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="763a0-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="763a0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="763a0-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="763a0-123">See also</span></span>

- [<span data-ttu-id="763a0-124">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="763a0-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="763a0-125">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="763a0-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="763a0-126">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="763a0-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
