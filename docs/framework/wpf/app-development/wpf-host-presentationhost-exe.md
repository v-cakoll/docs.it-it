---
title: Host WPF (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: 88e4c6895039c84a57ed215a37a10a4b68851b2d
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817920"
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="cc688-102">Host WPF (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="cc688-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="cc688-103">L'host Windows Presentation Foundation (WPF) (PresentationHost. exe) è l'applicazione che [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consente l'hosting di applicazioni in browser compatibili (incluso Microsoft Internet Explorer 6 e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="cc688-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including Microsoft Internet Explorer 6 and later).</span></span> <span data-ttu-id="cc688-104">Per impostazione predefinita, l'host Windows Presentation Foundation (WPF) viene registrato come shell [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] e gestore per il contenuto [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ospitato dal browser, che include:</span><span class="sxs-lookup"><span data-stu-id="cc688-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
- <span data-ttu-id="cc688-105">File [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separati (con estensione xaml) non compilati.</span><span class="sxs-lookup"><span data-stu-id="cc688-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
- <span data-ttu-id="cc688-106">File [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] (con estensione xbap).</span><span class="sxs-lookup"><span data-stu-id="cc688-106">[!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] (.xbap).</span></span>  
  
 <span data-ttu-id="cc688-107">Per i file di questi tipi, Windows Presentation Foundation host (WPF):</span><span class="sxs-lookup"><span data-stu-id="cc688-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
- <span data-ttu-id="cc688-108">Avvia il gestore HTML registrato per ospitare il contenuto del Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="cc688-108">Launches the registered HTML handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
- <span data-ttu-id="cc688-109">Carica le versioni corrette degli assembly Common Language Runtime (CLR) e Windows Presentation Foundation (WPF) richiesti.</span><span class="sxs-lookup"><span data-stu-id="cc688-109">Loads the right versions of the required common language runtime (CLR) and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
- <span data-ttu-id="cc688-110">Assicura che siano disponibili i livelli di autorizzazione appropriati per l'area di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cc688-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="cc688-111">Questo argomento descrive i parametri della riga di comando che è possibile utilizzare con PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="cc688-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="cc688-112">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="cc688-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="cc688-113">Parametri</span><span class="sxs-lookup"><span data-stu-id="cc688-113">Parameters</span></span>  
  
|<span data-ttu-id="cc688-114">Parametro</span><span class="sxs-lookup"><span data-stu-id="cc688-114">Parameter</span></span>|<span data-ttu-id="cc688-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="cc688-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cc688-116">filename</span><span class="sxs-lookup"><span data-stu-id="cc688-116">filename</span></span>|<span data-ttu-id="cc688-117">Il percorso del file da attivare.</span><span class="sxs-lookup"><span data-stu-id="cc688-117">The path of the file to be activated.</span></span> <span data-ttu-id="cc688-118">Può anche essere un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc688-118">Can also be a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>|  
|<span data-ttu-id="cc688-119">-debug</span><span class="sxs-lookup"><span data-stu-id="cc688-119">-debug</span></span>|<span data-ttu-id="cc688-120">Quando si attiva un'applicazione, non esegue il commit o non lo esegue dall'archivio.</span><span class="sxs-lookup"><span data-stu-id="cc688-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="cc688-121">Funziona solo quando un file locale è attivato.</span><span class="sxs-lookup"><span data-stu-id="cc688-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="cc688-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="cc688-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="cc688-123">Utilizzato con un valore [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] per indicare a PresentationHost.exe che un'applicazione dovrebbe essere sottoposta a debug come se fosse distribuita dall'[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] specificato.</span><span class="sxs-lookup"><span data-stu-id="cc688-123">Used with a [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span></span> <span data-ttu-id="cc688-124">In questo modo si determina l'area di distribuzione e il sito di origine.</span><span class="sxs-lookup"><span data-stu-id="cc688-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="cc688-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="cc688-125">-embedding</span></span>|<span data-ttu-id="cc688-126">Richiesto da OLE.</span><span class="sxs-lookup"><span data-stu-id="cc688-126">Required by OLE.</span></span> <span data-ttu-id="cc688-127">Se viene specificato il parametro `-event` o `-debug`, non è necessario specificare il parametro `-embedding`, poiché tale parametro è impostato internamente.</span><span class="sxs-lookup"><span data-stu-id="cc688-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="cc688-128">-event \<nomeevento></span><span class="sxs-lookup"><span data-stu-id="cc688-128">-event \<eventname></span></span>|<span data-ttu-id="cc688-129">Aprire l'evento con questo nome e segnalarlo quando PresentationHost.exe è inizializzato e pronto per ospitare il contenuto [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc688-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="cc688-130">PresentationHost.exe verrà chiuso se si verifica un errore durante l'apertura dell'evento, ad esempio come se non fosse stato creato.</span><span class="sxs-lookup"><span data-stu-id="cc688-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="cc688-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="cc688-131">-launchApplication \<url></span></span>|<span data-ttu-id="cc688-132">Avvia un'applicazione ClickOnce autonoma dall'URL specificato.</span><span class="sxs-lookup"><span data-stu-id="cc688-132">Launches a standalone ClickOnce application from the specified URL.</span></span> <span data-ttu-id="cc688-133">Vengono applicati i criteri di sicurezza di Internet Explorer e WinINet relativi alle applicazioni .NET.</span><span class="sxs-lookup"><span data-stu-id="cc688-133">Internet Explorer and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="cc688-134">Scenari</span><span class="sxs-lookup"><span data-stu-id="cc688-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="cc688-135">Gestore shell</span><span class="sxs-lookup"><span data-stu-id="cc688-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="cc688-136">Gestore MIME</span><span class="sxs-lookup"><span data-stu-id="cc688-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="cc688-137">Debug di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cc688-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="cc688-138">Debugging nell'area di sicurezza di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cc688-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="cc688-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc688-139">See also</span></span>

- [<span data-ttu-id="cc688-140">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cc688-140">Security</span></span>](../security-wpf.md)
