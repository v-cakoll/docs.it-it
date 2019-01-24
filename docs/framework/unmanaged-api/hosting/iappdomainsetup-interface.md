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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef967039450c77b5927d501de63d53a245c90be0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509831"
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="c4df1-102">Interfaccia IAppDomainSetup</span><span class="sxs-lookup"><span data-stu-id="c4df1-102">IAppDomainSetup Interface</span></span>
<span data-ttu-id="c4df1-103">Fornisce proprietà che consentono all'host configurare un <xref:System.AppDomain?displayProperty=nameWithType> tipo prima di chiamare il [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) metodo per la sua creazione.</span><span class="sxs-lookup"><span data-stu-id="c4df1-103">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c4df1-104">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c4df1-104">Properties</span></span>  
  
|<span data-ttu-id="c4df1-105">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c4df1-105">Property</span></span>|<span data-ttu-id="c4df1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4df1-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="c4df1-107">Ottiene o imposta il nome della directory che contiene l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c4df1-107">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="c4df1-108">Ottiene o imposta il nome dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c4df1-108">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="c4df1-109">Ottiene o imposta il nome di un'area specifica per l'applicazione, in cui i file sono una copia shadow.</span><span class="sxs-lookup"><span data-stu-id="c4df1-109">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="c4df1-110">Ottiene o imposta il nome del file di configurazione per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c4df1-110">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="c4df1-111">Ottiene o imposta il nome della directory in cui i file generati dinamicamente sono archiviati e accessibili.</span><span class="sxs-lookup"><span data-stu-id="c4df1-111">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="c4df1-112">Ottiene o imposta il percorso del file di licenza che è associato a questo dominio.</span><span class="sxs-lookup"><span data-stu-id="c4df1-112">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="c4df1-113">Ottiene o imposta l'elenco delle directory combinato con il <xref:System.AppDomainSetup.ApplicationBase%2A> directory per verificare la presenza di assembly privati.</span><span class="sxs-lookup"><span data-stu-id="c4df1-113">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="c4df1-114">Ottiene o imposta un valore stringa che include o esclude <xref:System.AppDomainSetup.ApplicationBase%2A> dal percorso di ricerca per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c4df1-114">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="c4df1-115">Ottiene o imposta i nomi delle directory contenenti gli assembly per la copia shadow.</span><span class="sxs-lookup"><span data-stu-id="c4df1-115">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="c4df1-116">Ottiene o imposta una stringa che indica se la copia shadow è attivata o disattivata.</span><span class="sxs-lookup"><span data-stu-id="c4df1-116">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="c4df1-117">I valori validi sono "true" o "false".</span><span class="sxs-lookup"><span data-stu-id="c4df1-117">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4df1-118">Note</span><span class="sxs-lookup"><span data-stu-id="c4df1-118">Remarks</span></span>  
 <span data-ttu-id="c4df1-119">Il `IAppDomainSetup` interfaccia corrisponde a quella gestita <xref:System.IAppDomainSetup> un'interfaccia, quale la <xref:System.AppDomainSetup> il tipo implementa.</span><span class="sxs-lookup"><span data-stu-id="c4df1-119">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="c4df1-120">Vedere <xref:System.IAppDomainSetup?displayProperty=nameWithType> per una descrizione dettagliata delle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="c4df1-120">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 <span data-ttu-id="c4df1-121">`IAppDomainSetup` rappresenta le informazioni di associazione di assembly che possono essere aggiunti a un <xref:System.AppDomain> istanza prima della sua creazione.</span><span class="sxs-lookup"><span data-stu-id="c4df1-121">`IAppDomainSetup` represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="c4df1-122">Ad esempio, un host può impostare il <xref:System.AppDomainSetup.ApplicationBase%2A> proprietà per stabilire una directory radice in cui i probe di common language runtime (CLR) per gli assembly gestiti.</span><span class="sxs-lookup"><span data-stu-id="c4df1-122">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4df1-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c4df1-123">Requirements</span></span>  
 <span data-ttu-id="c4df1-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4df1-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4df1-125">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c4df1-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4df1-126">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c4df1-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4df1-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4df1-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4df1-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4df1-128">See also</span></span>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [<span data-ttu-id="c4df1-129">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="c4df1-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
