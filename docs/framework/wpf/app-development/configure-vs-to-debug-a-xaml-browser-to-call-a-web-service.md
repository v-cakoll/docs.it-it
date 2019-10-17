---
title: "Procedura: configurare Visual Studio per eseguire il debug di un'applicazione browser XAML in grado di chiamare un servizio Web"
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: 7730ab452e227b11e5a9dd69cdabec51f333ce4f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321203"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Procedura: configurare Visual Studio per eseguire il debug di un'applicazione browser XAML in grado di chiamare un servizio Web
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] eseguiti in una sandbox di sicurezza con attendibilità parziale limitata al set di autorizzazioni dell'area Internet. Questo set di autorizzazioni limita le chiamate al servizio Web solo ai servizi Web che si trovano nel sito di origine dell'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Quando si esegue il debug di un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] da Visual Studio 2005, tuttavia, non si considera lo stesso sito di origine del servizio Web a cui fa riferimento. In questo modo vengono generate eccezioni di sicurezza quando il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] tenta di chiamare il servizio Web. Tuttavia, è possibile configurare un progetto di [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] di Visual Studio 2005 per simulare la presenza dello stesso sito di origine del servizio Web chiamato durante il debug. Ciò consente al [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] di chiamare in modo sicuro il servizio Web senza causare eccezioni di sicurezza.

## <a name="configuring-visual-studio"></a>Configurazione di Visual Studio 2017
 Per configurare Visual Studio 2005 per eseguire il debug di un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] che chiama un servizio Web:

1. Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.

2. In **Progettazione progetti**fare clic sulla scheda **debug** .

3. Nella sezione **azione di avvio** selezionare **Avvia programma esterno** e immettere quanto segue:

     `C:\WINDOWS\System32\PresentationHost.exe`

4. Nella sezione **Opzioni di avvio** immettere quanto segue nella casella di testo **argomenti della riga di comando** :

     *nome file* `-debug`

     Il valore del *nome file* per il parametro **-debug** è il nome file. XBAP; Per esempio:

     `-debug c:\example.xbap`

> [!NOTE]
> Questa è la configurazione predefinita per le soluzioni create con il modello di progetto di Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)].

1. Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.

2. In **Progettazione progetti**fare clic sulla scheda **debug** .

3. Nella sezione **Opzioni di avvio** aggiungere il parametro della riga di comando seguente alla casella di testo **argomenti della riga di comando** :

     `-debugSecurityZoneURL`  *URL*

     Il valore *URL* per il parametro **-DEBUGSECURITYZONEURL** è l'URL per la posizione che si vuole simulare come sito di origine dell'applicazione.

 Si consideri ad esempio un [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] che utilizza un servizio Web con l'URL seguente:

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 L'URL del sito di origine per questo servizio Web è:

 `http://services.msdn.microsoft.com`

 Di conseguenza, il parametro e il valore della riga di comando complete **-debugSecurityZoneURL** sono:

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a>Vedere anche

- [Host WPF (PresentationHost.exe)](wpf-host-presentationhost-exe.md)
