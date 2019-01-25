---
title: Componenti aggiuntivi di Firefox per supportare la distribuzione di applicazioni .NET
ms.date: 03/30/2017
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
ms.openlocfilehash: 31c6313adb24cd1a2cfca319ac5e243fcdf2b6a7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583259"
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>Componenti aggiuntivi di Firefox per supportare la distribuzione di applicazioni .NET
Abilitare Windows Presentation Foundation (WPF) plug-in per Firefox e .NET Framework Assistant per Firefox [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)], separato [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]e le applicazioni ClickOnce per lavorare con il browser Mozilla Firefox.  
  
## <a name="wpf-plug-in-for-firefox"></a>Plug-in per Firefox WPF  
 Il plug-in per Firefox WPF consente [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] e regime [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file per essere aperto ed eseguito al livello superiore o in un elemento IFRAME HTML nel browser Firefox. Un' [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] è un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione che può essere pubblicati in un server Web e avviata nel browser supportati. Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è un file XAML sola che può essere aperto e visualizzato nel browser supportati, molto simile a un file XML.  
  
 Il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plug-in per Firefox è installato con il [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]. Windows 7 include la [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], ma non include il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plug-in per Firefox. Non è possibile installare il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plug-in per Firefox in Windows 7.  
  
 Il [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] non include il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plug-in per Firefox. Tuttavia, se entrambi il [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] e [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] sono installati, WPF plug-in per Firefox è installato con il [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]. Di conseguenza [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] le applicazioni verranno ancora eseguite perché l'Host WPF caricherà la versione corretta del framework. Per altre informazioni, vedere [Host WPF (PresentationHost.exe)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md).  
  
## <a name="net-framework-assistant-for-firefox"></a>.NET Framework Assistant per Firefox  
 .NET Framework Assistant per Firefox Abilita autonomo di applicazioni ClickOnce per l'esecuzione dal browser Firefox. .NET Framework Assistant per Firefox funziona esattamente quando deve essere installata prima e dopo che il browser Firefox. Quando viene avviato il browser Firefox e [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] è installato, viene trovato e installa .NET Framework Assistant per Firefox. Gli utenti possono configurare .NET Framework Assistant per Firefox seguire questa procedura:  
  
-   Chiedi conferma prima di eseguire l'applicazione ClickOnce.  
  
-   Report tutte le versioni installate di .NET Framework o solo la versione più recente.  
  
 .NET Framework Assistant per Firefox è incluso con il [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]. Per informazioni sulla rimozione di .NET Framework Assistant per Firefox, vedere [come rimuovere .NET Framework Assistant per Firefox](https://go.microsoft.com/fwlink/?LinkId=177944).  
  
## <a name="see-also"></a>Vedere anche
- [Distribuzione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)
- [Panoramica delle applicazioni browser XAML di WPF](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)
- [Verificare se il plug-in delle applicazioni WPF per Firefox è installato](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
