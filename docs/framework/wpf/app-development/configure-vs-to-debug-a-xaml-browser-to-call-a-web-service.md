---
title: "Procedura: Configurare Visual Studio per eseguire il debug di un'applicazione browser XAML in grado di chiamare un servizio Web"
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: e41dd46e4ddbdcde6448c68b4f9fb2e073baca43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958682"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Procedura: Configurare Visual Studio per eseguire il debug di un'applicazione browser XAML in grado di chiamare un servizio Web
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]eseguire in una sandbox di sicurezza con attendibilità parziale limitata al set di autorizzazioni dell'area Internet. Questo set di autorizzazioni limita le [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] chiamate al servizio Web solo ai servizi Web che si trovano nel sito di origine dell'applicazione. Quando viene [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] eseguito il debug di un oggetto da Visual Studio 2005, tuttavia, non viene considerato lo stesso sito di origine del servizio Web a cui fa riferimento. In questo modo vengono generate eccezioni di sicurezza [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] quando si tenta di chiamare il servizio Web. Tuttavia, è possibile configurare un [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] progetto Visual Studio 2005 per simulare la presenza dello stesso sito di origine del servizio Web chiamato durante il debug. Ciò consente [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] a di chiamare in modo sicuro il servizio Web senza causare eccezioni di sicurezza.

## <a name="configuring-visual-studio"></a>Configurazione di Visual Studio 2017
 Per configurare Visual Studio 2005 per eseguire il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] debug di un oggetto che chiama un servizio Web:

1. Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.

2. In **Progettazione progetti**fare clic sulla scheda **debug** .

3. Nella sezione **azione di avvio** selezionare **Avvia programma esterno** e immettere quanto segue:

     `C:\WINDOWS\System32\PresentationHost.exe`

4. Nella sezione **Opzioni di avvio** immettere quanto segue nella casella di testo **argomenti della riga di comando** :

     `-debug`  *filename*

     Il valore del *nome file* per il parametro **-debug** è il nome file. XBAP; Per esempio:

     `-debug c:\example.xbap`

> [!NOTE]
> Questa è la configurazione predefinita per le soluzioni create con il modello di progetto di [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] Visual Studio 2005.

1. Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.

2. In **Progettazione progetti**fare clic sulla scheda **debug** .

3. Nella sezione **Opzioni di avvio** aggiungere il parametro della riga di comando seguente alla casella di testo **argomenti della riga di comando** :

     `-debugSecurityZoneURL`  *URL*

     Il valore dell' *URL* per il parametro **-debugSecurityZoneURL** è [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] l'oggetto per la posizione che si vuole simulare come sito di origine dell'applicazione.

 Si consideri ad esempio [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] un oggetto che utilizza un servizio Web con [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]quanto segue:

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 Il sito di origine [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] per questo servizio Web è:

 `http://services.msdn.microsoft.com`

 Di conseguenza, il parametro e il valore della riga di comando complete **-debugSecurityZoneURL** sono:

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a>Vedere anche

- [Host WPF (PresentationHost.exe)](wpf-host-presentationhost-exe.md)
