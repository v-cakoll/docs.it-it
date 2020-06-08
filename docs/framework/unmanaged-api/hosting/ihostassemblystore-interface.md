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
ms.openlocfilehash: cca73eec663b9afd12ecea5ab9d7073ea0168d33
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501557"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="1cd6b-102">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="1cd6b-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="1cd6b-103">Fornisce metodi che consentono a un host di caricare assembly e moduli indipendentemente dal Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="1cd6b-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1cd6b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="1cd6b-104">Methods</span></span>  
  
|<span data-ttu-id="1cd6b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="1cd6b-105">Method</span></span>|<span data-ttu-id="1cd6b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cd6b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1cd6b-107">Metodo ProvideAssembly</span><span class="sxs-lookup"><span data-stu-id="1cd6b-107">ProvideAssembly Method</span></span>](ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="1cd6b-108">Ottiene un riferimento a un assembly a cui non fa riferimento [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) restituito da una chiamata a [IHostAssemblyManager:: GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="1cd6b-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="1cd6b-109">Metodo ProvideModule</span><span class="sxs-lookup"><span data-stu-id="1cd6b-109">ProvideModule Method</span></span>](ihostassemblystore-providemodule-method.md)|<span data-ttu-id="1cd6b-110">Risolve un modulo all'interno di un assembly o di un file di risorse collegato (non incorporato).</span><span class="sxs-lookup"><span data-stu-id="1cd6b-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cd6b-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1cd6b-111">Remarks</span></span>  
 <span data-ttu-id="1cd6b-112">`IHostAssemblyStore`consente a un host di caricare gli assembly in modo efficiente in base all'identità dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="1cd6b-113">L'host carica gli assembly restituendo `IStream` istanze che puntano direttamente ai byte.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="1cd6b-114">CLR determina se un host è stato implementato chiamando `IHostAssemblyStore` `IHostAssemblyManager::GetNonHostAssemblyStores` al momento dell'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="1cd6b-115">Questo consente all'host, ad esempio, di controllare l'associazione agli assembly utente, ma di basarsi sul runtime per eseguire l'associazione a .NET Framework assembly.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1cd6b-116">Per fornire un'implementazione di `IHostAssemblyStore` , l'host specifica la finalità di risolvere tutti gli assembly a cui non viene fatto riferimento dal `ICLRAssemblyReferenceList` restituito da `IHostAssemblyManager::GetNonHostStoreAssemblies` .</span><span class="sxs-lookup"><span data-stu-id="1cd6b-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1cd6b-117">Il .NET Framework versione 2,0 non consente all'host di caricare l'immagine nativa di un assembly, come specificato dall'utilità [Generatore di immagini native (Ngen. exe)](../../tools/ngen-exe-native-image-generator.md) .</span><span class="sxs-lookup"><span data-stu-id="1cd6b-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cd6b-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1cd6b-118">Requirements</span></span>  
 <span data-ttu-id="1cd6b-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cd6b-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cd6b-120">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1cd6b-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1cd6b-121">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1cd6b-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1cd6b-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cd6b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd6b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cd6b-123">See also</span></span>

- [<span data-ttu-id="1cd6b-124">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="1cd6b-124">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="1cd6b-125">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="1cd6b-125">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="1cd6b-126">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="1cd6b-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
