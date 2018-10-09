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
ms.openlocfilehash: 182ceb96385bdca74d1d5c20079f78fe589982cf
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2018
ms.locfileid: "48873203"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Procedura: configurare Visual Studio per eseguire il debug di un'applicazione browser XAML in grado di chiamare un servizio Web
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] eseguire in una sandbox di sicurezza con attendibilità parziale limitata al set di autorizzazioni area Internet. Questo set di autorizzazioni limita chiamate ai servizi Web che si trovano in servizi Web di [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] sito di origine dell'applicazione. Quando un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] viene eseguito il debug da Visual Studio 2005, tuttavia, non viene considerata come avere stesso sito di origine come servizio Web a cui fa riferimento. Le eccezioni di sicurezza questo cause da generare quando il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] tenta di chiamare il servizio Web. Tuttavia, un Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] progetto può essere configurato per simulare la presenza di stesso sito di origine come il servizio Web chiamato durante il debug. In questo modo il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] per chiamare il servizio Web senza che vengano generate eccezioni di sicurezza.

## <a name="configuring-visual-studio"></a>Configurazione di Visual Studio
 Per configurare Visual Studio 2005, eseguire il debug di un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] che chiama un servizio Web:

1.  Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.

2.  Nel **creazione progetti**, fare clic sui **Debug** scheda.

3.  Nel **azione di avvio** sezione, selezionare **Avvia programma esterno** e immettere le informazioni seguenti:

     `C:\WINDOWS\System32\PresentationHost.exe`

4.  Nel **opzioni di avvio** sezione, immettere quanto segue nel **argomenti della riga di comando** casella di testo:

     `-debug`  *Nome del file*

     Il *nomefile* valore per il **-debug** parametro è il nome del file con estensione xbap, ad esempio:

     `-debug c:\example.xbap`

> [!NOTE]
>  Questa è la configurazione predefinita per le soluzioni create con Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] modello di progetto.

1.  Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.

2.  Nel **creazione progetti**, fare clic sui **Debug** scheda.

3.  Nel **opzioni di avvio** sezione, aggiungere il parametro della riga di comando seguente per il **argomenti della riga di comando** casella di testo:

     `-debugSecurityZoneURL`  *URL*

     Il *URL* valore per il **- debugSecurityZoneURL** parametro è il [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] per il percorso che si desidera simulare come sito di origine dell'applicazione.

 Ad esempio, prendere in considerazione una [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] che usa un servizio Web con il codice seguente [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 Il sito di origine [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] per questo sito Web servizio è:

 `http://services.msdn.microsoft.com`

 Di conseguenza, l'intero **debugSecurityZoneURL -** parametro della riga di comando e il valore è:

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a>Vedere anche
 [Host WPF (PresentationHost.exe)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)
