---
title: Interfaccia IHostAssemblyStore
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore
helpviewer_keywords: IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c795d4baa3030817299f23c3dadf4caf7a5edc5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="ca61c-102">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="ca61c-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="ca61c-103">Fornisce metodi che consentono a un host caricare gli assembly e moduli in modo indipendente da common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ca61c-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca61c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ca61c-104">Methods</span></span>  
  
|<span data-ttu-id="ca61c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ca61c-105">Method</span></span>|<span data-ttu-id="ca61c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca61c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca61c-107">Metodo ProvideAssembly</span><span class="sxs-lookup"><span data-stu-id="ca61c-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="ca61c-108">Ottiene un riferimento a un assembly che non fa riferimento il [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) restituito da una chiamata a [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="ca61c-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="ca61c-109">Metodo ProvideModule</span><span class="sxs-lookup"><span data-stu-id="ca61c-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="ca61c-110">Risolve un modulo all'interno di un assembly o un file di risorse (non incorporato) collegati.</span><span class="sxs-lookup"><span data-stu-id="ca61c-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca61c-111">Note</span><span class="sxs-lookup"><span data-stu-id="ca61c-111">Remarks</span></span>  
 <span data-ttu-id="ca61c-112">`IHostAssemblyStore`fornisce un modo per un host caricare gli assembly efficiente in base all'identità dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ca61c-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="ca61c-113">L'host carica gli assembly restituendo `IStream` istanze che puntano direttamente i byte.</span><span class="sxs-lookup"><span data-stu-id="ca61c-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="ca61c-114">Common Language Runtime determina se un host ha implementato `IHostAssemblyStore` chiamando `IHostAssemblyManager::GetNonHostAssemblyStores` al momento dell'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="ca61c-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="ca61c-115">Ciò consente all'host, ad esempio, per controllare l'associazione di assembly dell'utente, ma per cui si basano sull'ambiente di esecuzione per l'associazione agli assembly .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca61c-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca61c-116">Fornendo un'implementazione di `IHostAssemblyStore`, l'host specifica l'intento di risolvere tutti gli assembly che non fa riferimento il `ICLRAssemblyReferenceList` restituito da `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="ca61c-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca61c-117">.NET Framework versione 2.0 non fornisce un modo per caricare l'immagine nativa di un assembly, l'host fornito dal [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utilità.</span><span class="sxs-lookup"><span data-stu-id="ca61c-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca61c-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca61c-118">Requirements</span></span>  
 <span data-ttu-id="ca61c-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca61c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca61c-120">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="ca61c-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca61c-121">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ca61c-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca61c-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca61c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca61c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca61c-123">See Also</span></span>  
 [<span data-ttu-id="ca61c-124">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="ca61c-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="ca61c-125">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="ca61c-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="ca61c-126">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="ca61c-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
