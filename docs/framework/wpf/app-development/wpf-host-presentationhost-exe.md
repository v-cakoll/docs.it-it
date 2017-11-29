---
title: Host WPF (PresentationHost.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b7662213d7204675de7e8681b6fc8141f04dd21
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="4a98b-102">Host WPF (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="4a98b-102">WPF Host (PresentationHost.exe)</span></span>
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]<span data-ttu-id="4a98b-103"> Host (PresentationHost.exe) è l'applicazione che consente alle applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] di essere ospitate in browser compatibili (inclusi [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="4a98b-103"> Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] and later).</span></span> <span data-ttu-id="4a98b-104">Per impostazione predefinita, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host è registrato come la shell e il gestore [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] per il contenuto [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ospitato da browser, tra cui:</span><span class="sxs-lookup"><span data-stu-id="4a98b-104">By default, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host is registered as the shell and [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
-   <span data-ttu-id="4a98b-105">File [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separati (con estensione xaml) non compilati.</span><span class="sxs-lookup"><span data-stu-id="4a98b-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
-   <span data-ttu-id="4a98b-106">File [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] (con estensione xbap).</span><span class="sxs-lookup"><span data-stu-id="4a98b-106">[!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] (.xbap).</span></span>  
  
 <span data-ttu-id="4a98b-107">Per file di questi tipi, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host:</span><span class="sxs-lookup"><span data-stu-id="4a98b-107">For files of these types, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host:</span></span>  
  
-   <span data-ttu-id="4a98b-108">Avvia il gestore [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] registrato per ospitare il contenuto [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a98b-108">Launches the registered [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] handler to host the [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] content.</span></span>  
  
-   <span data-ttu-id="4a98b-109">Carica le versioni corrette degli assembly [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] e [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] necessari.</span><span class="sxs-lookup"><span data-stu-id="4a98b-109">Loads the right versions of the required [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] and [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] assemblies.</span></span>  
  
-   <span data-ttu-id="4a98b-110">Assicura che siano disponibili i livelli di autorizzazione appropriati per l'area di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4a98b-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="4a98b-111">Questo argomento descrive i parametri della riga di comando che è possibile utilizzare con PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="4a98b-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="4a98b-112">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="4a98b-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="4a98b-113">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a98b-113">Parameters</span></span>  
  
|<span data-ttu-id="4a98b-114">Parametro</span><span class="sxs-lookup"><span data-stu-id="4a98b-114">Parameter</span></span>|<span data-ttu-id="4a98b-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a98b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a98b-116">filename</span><span class="sxs-lookup"><span data-stu-id="4a98b-116">filename</span></span>|<span data-ttu-id="4a98b-117">Il percorso del file da attivare.</span><span class="sxs-lookup"><span data-stu-id="4a98b-117">The path of the file to be activated.</span></span> <span data-ttu-id="4a98b-118">Può anche essere un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a98b-118">Can also be a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>|  
|<span data-ttu-id="4a98b-119">-debug</span><span class="sxs-lookup"><span data-stu-id="4a98b-119">-debug</span></span>|<span data-ttu-id="4a98b-120">Quando si attiva un'applicazione, non esegue il commit o non lo esegue dall'archivio.</span><span class="sxs-lookup"><span data-stu-id="4a98b-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="4a98b-121">Funziona solo quando un file locale è attivato.</span><span class="sxs-lookup"><span data-stu-id="4a98b-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="4a98b-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="4a98b-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="4a98b-123">Utilizzato con un valore [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] per indicare a PresentationHost.exe che un'applicazione dovrebbe essere sottoposta a debug come se fosse distribuita dall'[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] specificato.</span><span class="sxs-lookup"><span data-stu-id="4a98b-123">Used with a [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span></span> <span data-ttu-id="4a98b-124">In questo modo si determina l'area di distribuzione e il sito di origine.</span><span class="sxs-lookup"><span data-stu-id="4a98b-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="4a98b-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="4a98b-125">-embedding</span></span>|<span data-ttu-id="4a98b-126">Richiesto da OLE.</span><span class="sxs-lookup"><span data-stu-id="4a98b-126">Required by OLE.</span></span> <span data-ttu-id="4a98b-127">Se viene specificato il parametro `-event` o `-debug`, non è necessario specificare il parametro `-embedding`, poiché tale parametro è impostato internamente.</span><span class="sxs-lookup"><span data-stu-id="4a98b-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="4a98b-128">-event \<nomeevento></span><span class="sxs-lookup"><span data-stu-id="4a98b-128">-event \<eventname></span></span>|<span data-ttu-id="4a98b-129">Aprire l'evento con questo nome e segnalarlo quando PresentationHost.exe è inizializzato e pronto per ospitare il contenuto [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a98b-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="4a98b-130">PresentationHost.exe verrà chiuso se si verifica un errore durante l'apertura dell'evento, ad esempio come se non fosse stato creato.</span><span class="sxs-lookup"><span data-stu-id="4a98b-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="4a98b-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="4a98b-131">-launchApplication \<url></span></span>|<span data-ttu-id="4a98b-132">Avvia un'applicazione [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] autonoma dall'URL specificato.</span><span class="sxs-lookup"><span data-stu-id="4a98b-132">Launches a standalone [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] application from the specified URL.</span></span> <span data-ttu-id="4a98b-133">Vengono applicati i criteri di sicurezza di [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] e WinINet relativi alle applicazioni .NET.</span><span class="sxs-lookup"><span data-stu-id="4a98b-133">[!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="4a98b-134">Scenari</span><span class="sxs-lookup"><span data-stu-id="4a98b-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="4a98b-135">Gestore shell</span><span class="sxs-lookup"><span data-stu-id="4a98b-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="4a98b-136">Gestore MIME</span><span class="sxs-lookup"><span data-stu-id="4a98b-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="4a98b-137">Debug di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4a98b-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="4a98b-138">Debugging nell'area di sicurezza di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4a98b-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="4a98b-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a98b-139">See Also</span></span>  
 [<span data-ttu-id="4a98b-140">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4a98b-140">Security</span></span>](../../../../docs/framework/wpf/security-wpf.md)
