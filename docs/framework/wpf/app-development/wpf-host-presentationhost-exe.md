---
title: Host WPF (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: 543076c3b00bf7946111df4c18d8c71928ce7ee2
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487320"
---
# <a name="wpf-host-presentationhostexe"></a>Host WPF (PresentationHost.exe)
Host di Windows Presentation Foundation (WPF) (PresentationHost.exe) è l'applicazione che consente [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] alle applicazioni di essere ospitate in browser compatibili (inclusi [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] e versioni successive). Per impostazione predefinita, l'Host di Windows Presentation Foundation (WPF) è registrato come la shell e [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] ospitate da browser gestore per [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] contenuto, che include:  
  
- File [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separati (con estensione xaml) non compilati.  
  
- File [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] (con estensione xbap).  
  
 Per i file di questi tipi, Host di Windows Presentation Foundation (WPF):  
  
- Avvia l'oggetto registrato [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] gestore per ospitare il contenuto di Windows Presentation Foundation (WPF).  
  
- Carica le versioni corrette degli richiesti [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] e gli assembly di Windows Presentation Foundation (WPF).  
  
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
|-launchApplication \<url>|Avvia un'applicazione ClickOnce dall'URL specificato autonoma. Vengono applicati i criteri di sicurezza di [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] e WinINet relativi alle applicazioni .NET.|  
  
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
