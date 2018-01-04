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
ms.workload: dotnet
ms.openlocfilehash: 1c5a9df438353701932a3e732d6df28b08402ee8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="wpf-host-presentationhostexe"></a>Host WPF (PresentationHost.exe)
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host (PresentationHost.exe) è l'applicazione che consente alle applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] di essere ospitate in browser compatibili (inclusi [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] e versioni successive). Per impostazione predefinita, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host è registrato come la shell e il gestore [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] per il contenuto [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ospitato da browser, tra cui:  
  
-   File [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separati (con estensione xaml) non compilati.  
  
-   File [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] (con estensione xbap).  
  
 Per file di questi tipi, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host:  
  
-   Avvia il gestore [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] registrato per ospitare il contenuto [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  
  
-   Carica le versioni corrette degli assembly [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] e [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] necessari.  
  
-   Assicura che siano disponibili i livelli di autorizzazione appropriati per l'area di distribuzione.  
  
 Questo argomento descrive i parametri della riga di comando che è possibile utilizzare con PresentationHost.exe.  
  
## <a name="usage"></a>Utilizzo  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a>Parametri  
  
|Parametro|Descrizione|  
|---------------|-----------------|  
|filename|Il percorso del file da attivare. Può anche essere un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].|  
|-debug|Quando si attiva un'applicazione, non esegue il commit o non lo esegue dall'archivio. Funziona solo quando un file locale è attivato.|  
|-debugSecurityZoneURL \<url>|Utilizzato con un valore [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] per indicare a PresentationHost.exe che un'applicazione dovrebbe essere sottoposta a debug come se fosse distribuita dall'[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] specificato. In questo modo si determina l'area di distribuzione e il sito di origine.|  
|-embedding|Richiesto da OLE. Se viene specificato il parametro `-event` o `-debug`, non è necessario specificare il parametro `-embedding`, poiché tale parametro è impostato internamente.|  
|-event \<nomeevento>|Aprire l'evento con questo nome e segnalarlo quando PresentationHost.exe è inizializzato e pronto per ospitare il contenuto [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. PresentationHost.exe verrà chiuso se si verifica un errore durante l'apertura dell'evento, ad esempio come se non fosse stato creato.|  
|-launchApplication \<url>|Avvia un'applicazione [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] autonoma dall'URL specificato. Vengono applicati i criteri di sicurezza di [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] e WinINet relativi alle applicazioni .NET.|  
  
## <a name="scenarios"></a>Scenari  
  
### <a name="shell-handler"></a>Gestore shell  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a>Gestore MIME  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a>Debug di Visual Studio  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a>Debugging nell'area di sicurezza di Visual Studio  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a>Vedere anche  
 [Sicurezza](../../../../docs/framework/wpf/security-wpf.md)
