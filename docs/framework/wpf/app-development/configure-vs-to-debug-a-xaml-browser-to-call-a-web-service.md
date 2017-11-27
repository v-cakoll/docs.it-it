---
title: 'Procedura: configurare Visual Studio per eseguire il debug di un''applicazione browser XAML in grado di chiamare un servizio Web'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5db89cf6220f086d2d71b99f3e6440e584d6a5d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Procedura: configurare Visual Studio per eseguire il debug di un'applicazione browser XAML in grado di chiamare un servizio Web
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]eseguire in una sandbox di sicurezza con attendibilità parziale è limitata al set di autorizzazioni area Internet. Questo set di autorizzazioni limita le chiamate di servizio Web per servizi Web che si trovano nel [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] sito di origine dell'applicazione. Quando un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] è sottoposta a debug da [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)], tuttavia, non è considerato hanno lo stesso sito di origine come servizio Web a cui fa riferimento. Eccezioni di sicurezza questo cause per essere generato quando il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] tenta di chiamare il servizio Web. Tuttavia, un [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] progetto può essere configurato per simulare la presenza di stesso sito di origine il servizio Web chiamato durante il debug. In questo modo il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] per chiamare il servizio Web senza provocare eccezioni di sicurezza.  
  
## <a name="configuring-visual-studio"></a>Configurazione di Visual Studio  
 Per configurare [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] eseguire il debug di un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] che chiama un servizio Web:  
  
1.  Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.  
  
2.  Nel **progettazione**, fare clic su di **Debug** scheda.  
  
3.  Nel **azione di avvio** selezionare **Avvia programma esterno** e immettere quanto segue:  
  
     `C:\WINDOWS\System32\PresentationHost.exe`  
  
4.  Nel **opzioni di avvio** sezione, immettere quanto segue nel **argomenti della riga di comando** casella di testo:  
  
     `-debug`  *nome file*  
  
     Il *filename* valore per il **-debug** parametro è il nome del file xbap, ad esempio:  
  
     `-debug c:\example.xbap`  
  
> [!NOTE]
>  Questa è la configurazione predefinita per le soluzioni create con la [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] modello di progetto.  
  
1.  Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.  
  
2.  Nel **progettazione**, fare clic su di **Debug** scheda.  
  
3.  Nel **opzioni di avvio** sezione, aggiungere il parametro della riga di comando seguente per il **argomenti della riga di comando** casella di testo:  
  
     `-debugSecurityZoneURL`  *URL*  
  
     Il *URL* valore per il **- debugSecurityZoneURL** parametro è il [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] per il percorso che si desidera simulare come sito di origine dell'applicazione.  
  
 Ad esempio, si consideri un [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] che utilizza un servizio Web con il codice seguente [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:  
  
 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`  
  
 Il sito di origine [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] per questo sito Web servizio è:  
  
 `http://services.msdn.microsoft.com`  
  
 Di conseguenza, l'intero **- debugSecurityZoneURL** parametro della riga di comando e il valore è:  
  
 `-debugSecurityZoneURL http://services.msdn.microsoft.com`  
  
## <a name="see-also"></a>Vedere anche  
 [Host WPF (PresentationHost.exe)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)
