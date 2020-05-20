---
title: Interfaccia IAppDomainSetup
ms.date: 03/30/2017
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
ms.openlocfilehash: 1726f8929404e0dde979972d7830a6951dd71891
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617061"
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="d8dc3-102">Interfaccia IAppDomainSetup</span><span class="sxs-lookup"><span data-stu-id="d8dc3-102">IAppDomainSetup Interface</span></span>
<span data-ttu-id="d8dc3-103">Fornisce le proprietà che consentono all'host di configurare un <xref:System.AppDomain?displayProperty=nameWithType> tipo prima di chiamare il metodo [ICorRuntimeHost:: CreateDomainEx](icorruntimehost-createdomainex-method.md) per crearlo.</span><span class="sxs-lookup"><span data-stu-id="d8dc3-103">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d8dc3-104">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d8dc3-104">Properties</span></span>  
  
|<span data-ttu-id="d8dc3-105">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d8dc3-105">Property</span></span>|<span data-ttu-id="d8dc3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8dc3-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="d8dc3-107">Ottiene o imposta il nome della directory che contiene l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d8dc3-107">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="d8dc3-108">Ottiene o imposta il nome dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d8dc3-108">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="d8dc3-109">Ottiene o imposta il nome di un'area specifica per l'applicazione in cui viene eseguita la copia shadow dei file.</span><span class="sxs-lookup"><span data-stu-id="d8dc3-109">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="d8dc3-110">Ottiene o imposta il nome del file di configurazione per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d8dc3-110">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="d8dc3-111">Ottiene o imposta il nome della directory in cui vengono archiviati e accessibili i file generati dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="d8dc3-111">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="d8dc3-112">Ottiene o imposta il percorso del file di licenza associato al dominio.</span><span class="sxs-lookup"><span data-stu-id="d8dc3-112">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="d8dc3-113">Ottiene o imposta l'elenco di directory combinate con la <xref:System.AppDomainSetup.ApplicationBase%2A> directory in cui eseguire il probe degli assembly privati.</span><span class="sxs-lookup"><span data-stu-id="d8dc3-113">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="d8dc3-114">Ottiene o imposta un valore stringa che include o esclude <xref:System.AppDomainSetup.ApplicationBase%2A> dal percorso di ricerca dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d8dc3-114">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="d8dc3-115">Ottiene o imposta i nomi delle directory che contengono gli assembly di cui eseguire la copia shadow.</span><span class="sxs-lookup"><span data-stu-id="d8dc3-115">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="d8dc3-116">Ottiene o imposta una stringa che indica se la copia shadow è attivata o disattivata.</span><span class="sxs-lookup"><span data-stu-id="d8dc3-116">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="d8dc3-117">I valori validi sono "true" o "false".</span><span class="sxs-lookup"><span data-stu-id="d8dc3-117">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8dc3-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d8dc3-118">Remarks</span></span>  
 <span data-ttu-id="d8dc3-119">L' `IAppDomainSetup` interfaccia corrisponde all'interfaccia gestita <xref:System.IAppDomainSetup> , <xref:System.AppDomainSetup> implementata dal tipo.</span><span class="sxs-lookup"><span data-stu-id="d8dc3-119">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="d8dc3-120"><xref:System.IAppDomainSetup?displayProperty=nameWithType>Per una descrizione dettagliata delle proprietà, vedere.</span><span class="sxs-lookup"><span data-stu-id="d8dc3-120">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 <span data-ttu-id="d8dc3-121">`IAppDomainSetup`rappresenta le informazioni di associazione dell'assembly che possono essere aggiunte a un' <xref:System.AppDomain> istanza prima della creazione.</span><span class="sxs-lookup"><span data-stu-id="d8dc3-121">`IAppDomainSetup` represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="d8dc3-122">Un host può, ad esempio, impostare la <xref:System.AppDomainSetup.ApplicationBase%2A> proprietà per stabilire una directory radice, che il Common Language Runtime (CLR) esegue il probe per gli assembly gestiti.</span><span class="sxs-lookup"><span data-stu-id="d8dc3-122">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8dc3-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8dc3-123">Requirements</span></span>  
 <span data-ttu-id="d8dc3-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8dc3-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8dc3-125">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d8dc3-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8dc3-126">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d8dc3-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8dc3-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8dc3-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8dc3-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8dc3-128">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [<span data-ttu-id="d8dc3-129">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="d8dc3-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
