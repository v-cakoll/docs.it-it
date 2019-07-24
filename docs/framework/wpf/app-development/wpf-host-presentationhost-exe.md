---
title: Host WPF (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: 16618042324387bfc15f4685f4759378c50a80b7
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401712"
---
# <a name="wpf-host-presentationhostexe"></a>Host WPF (PresentationHost.exe)
L'host Windows Presentation Foundation (WPF) (PresentationHost. exe) è l'applicazione che [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consente di ospitare le applicazioni in browser compatibili ( [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] inclusi e versioni successive). Per impostazione predefinita, l'host Windows Presentation Foundation (WPF) viene registrato come shell [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] e gestore per il contenuto [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ospitato dal browser, che include:  
  
- File [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separati (con estensione xaml) non compilati.  
  
- File [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] (con estensione xbap).  
  
 Per i file di questi tipi, Windows Presentation Foundation host (WPF):  
  
- Avvia il gestore [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] registrato per ospitare il contenuto del Windows Presentation Foundation (WPF).  
  
- Carica le versioni corrette degli assembly Common Language Runtime (CLR) e Windows Presentation Foundation (WPF) richiesti.  
  
- Assicura che siano disponibili i livelli di autorizzazione appropriati per l'area di distribuzione.  
  
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
|-launchApplication \<url>|Avvia un'applicazione ClickOnce autonoma dall'URL specificato. Vengono applicati i criteri di sicurezza di [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] e WinINet relativi alle applicazioni .NET.|  
  
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

- [Sicurezza](../security-wpf.md)
