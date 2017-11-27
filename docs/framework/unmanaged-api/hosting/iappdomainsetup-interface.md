---
title: Interfaccia IAppDomainSetup
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAppDomainSetup
api_location: mscoree.dll
api_type: COM
f1_keywords: IAppDomainSetup
helpviewer_keywords: IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e6ed5ea00799fff70626114257efef2d06b505ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="3128a-102">Interfaccia IAppDomainSetup</span><span class="sxs-lookup"><span data-stu-id="3128a-102">IAppDomainSetup Interface</span></span>
<span data-ttu-id="3128a-103">Fornisce proprietà che consentono all'host configurare un <xref:System.AppDomain?displayProperty=nameWithType> tipo prima di chiamare il [ICorRuntimeHost:: CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) metodo per la sua creazione.</span><span class="sxs-lookup"><span data-stu-id="3128a-103">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3128a-104">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3128a-104">Properties</span></span>  
  
|<span data-ttu-id="3128a-105">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3128a-105">Property</span></span>|<span data-ttu-id="3128a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3128a-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="3128a-107">Ottiene o imposta il nome della directory che contiene l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3128a-107">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="3128a-108">Ottiene o imposta il nome dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3128a-108">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="3128a-109">Ottiene o imposta il nome di un'area specifica per l'applicazione, in cui i file vengono replicati.</span><span class="sxs-lookup"><span data-stu-id="3128a-109">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="3128a-110">Ottiene o imposta il nome del file di configurazione per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3128a-110">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="3128a-111">Ottiene o imposta il nome della directory in cui i file generati dinamicamente sono archiviati e accessibili.</span><span class="sxs-lookup"><span data-stu-id="3128a-111">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="3128a-112">Ottiene o imposta il percorso del file di licenza che è associato a questo dominio.</span><span class="sxs-lookup"><span data-stu-id="3128a-112">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="3128a-113">Ottiene o imposta l'elenco delle directory combinate con il <xref:System.AppDomainSetup.ApplicationBase%2A> directory per verificare la presenza di assembly privati.</span><span class="sxs-lookup"><span data-stu-id="3128a-113">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="3128a-114">Ottiene o imposta un valore stringa che include o esclude <xref:System.AppDomainSetup.ApplicationBase%2A> dal percorso di ricerca per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3128a-114">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="3128a-115">Ottiene o imposta i nomi delle directory contenenti assembly per la copia shadow.</span><span class="sxs-lookup"><span data-stu-id="3128a-115">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="3128a-116">Ottiene o imposta una stringa che indica se la copia shadow è attivata o disattivata.</span><span class="sxs-lookup"><span data-stu-id="3128a-116">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="3128a-117">I valori validi sono "true" o "false".</span><span class="sxs-lookup"><span data-stu-id="3128a-117">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3128a-118">Note</span><span class="sxs-lookup"><span data-stu-id="3128a-118">Remarks</span></span>  
 <span data-ttu-id="3128a-119">Il `IAppDomainSetup` interfaccia corrisponde a quella gestita <xref:System.IAppDomainSetup> interfaccia, quale il <xref:System.AppDomainSetup> il tipo implementa.</span><span class="sxs-lookup"><span data-stu-id="3128a-119">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="3128a-120">Vedere <xref:System.IAppDomainSetup?displayProperty=nameWithType> per una descrizione dettagliata delle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="3128a-120">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 <span data-ttu-id="3128a-121">`IAppDomainSetup`rappresenta le informazioni di associazione di assembly che possono essere aggiunti a un <xref:System.AppDomain> istanza prima della relativa creazione.</span><span class="sxs-lookup"><span data-stu-id="3128a-121">`IAppDomainSetup` represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="3128a-122">Ad esempio, è possibile impostare un host di <xref:System.AppDomainSetup.ApplicationBase%2A> proprietà per definire una directory radice, common language runtime (CLR) viene eseguita la ricerca di assembly gestiti.</span><span class="sxs-lookup"><span data-stu-id="3128a-122">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3128a-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3128a-123">Requirements</span></span>  
 <span data-ttu-id="3128a-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3128a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3128a-125">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="3128a-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3128a-126">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3128a-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3128a-127">**Versioni di .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3128a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3128a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3128a-128">See Also</span></span>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainSetup>  
 <xref:System.IAppDomainSetup>  
 [<span data-ttu-id="3128a-129">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="3128a-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
