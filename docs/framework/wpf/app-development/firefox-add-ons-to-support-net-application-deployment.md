---
title: Componenti aggiuntivi di Firefox per supportare la distribuzione di applicazioni .NET
ms.date: 03/30/2017
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
ms.openlocfilehash: f05f5afa0c0a7ef858442bd98233865834b8b89b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547443"
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>Componenti aggiuntivi di Firefox per supportare la distribuzione di applicazioni .NET
Abilitare Windows Presentation Foundation (WPF) plug-in per Firefox e .NET Framework Assistant per Firefox [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)], regime [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]e le applicazioni ClickOnce per funzionare con il browser Mozilla Firefox.  
  
## <a name="wpf-plug-in-for-firefox"></a>Plug-in per Firefox WPF  
 Il plug-in per Firefox WPF consente [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] e cavi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file e l'esecuzione al livello superiore o in un IFRAME HTML nel browser Firefox. Un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] è un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione che può essere pubblicato in un server Web e avviata nel browser supportati. Cavi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è un file solo XAML che può essere passato a e visualizzato nei browser supportati, analogamente a un file XML.  
  
 Il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plug-in per Firefox è installato con il [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]. Windows 7 include il [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], ma non include il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plug-in per Firefox. Non è possibile installare il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plug-in per Firefox in Windows 7.  
  
 Il [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] non include il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plug-in per Firefox. Tuttavia, se entrambi il [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] e [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] sono installati, il plug-in per Firefox WPF viene installato con il [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]. Pertanto [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] applicazioni continuerà ad essere eseguito perché l'Host WPF caricherà la versione corretta del framework. Per ulteriori informazioni, vedere [Host WPF (PresentationHost.exe)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md).  
  
## <a name="net-framework-assistant-for-firefox"></a>.NET Framework Assistant per Firefox  
 .NET Framework Assistant per Firefox consente l'esecuzione dal browser Firefox autonoma delle applicazioni ClickOnce. .NET Framework Assistant per Firefox funzioni in modo identico quando viene installato prima e dopo il browser Firefox. Quando viene avviato il browser Firefox e [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] è installato, viene trovato e installa .NET Framework Assistant per Firefox. Gli utenti possono configurare .NET Framework Assistant per Firefox per eseguire le operazioni seguenti:  
  
-   Chiedi conferma prima di eseguire l'applicazione ClickOnce.  
  
-   Report tutte le versioni installate di .NET Framework o solo la versione più recente.  
  
 .NET Framework Assistant per Firefox è incluso il [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]. Per informazioni sulla rimozione di .NET Framework Assistant per Firefox, vedere [come rimuovere .NET Framework Assistant per Firefox](http://go.microsoft.com/fwlink/?LinkId=177944).  
  
## <a name="see-also"></a>Vedere anche  
 [Distribuzione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)  
 [Panoramica delle applicazioni browser XAML di WPF](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)  
 [Verificare se il plug-in delle applicazioni WPF per Firefox è installato](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
