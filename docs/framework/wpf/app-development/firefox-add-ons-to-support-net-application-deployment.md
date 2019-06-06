---
title: Componenti aggiuntivi di Firefox per supportare la distribuzione di applicazioni .NET
ms.date: 03/30/2017
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
ms.openlocfilehash: e018048df70470e349f06ac80e7a597cd742dac5
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690510"
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>Componenti aggiuntivi di Firefox per supportare la distribuzione di applicazioni .NET
Abilitare Windows Presentation Foundation (WPF) plug-in per Firefox e .NET Framework Assistant per Firefox [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)], separato [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]e le applicazioni ClickOnce per lavorare con il browser Mozilla Firefox.  
  
## <a name="wpf-plug-in-for-firefox"></a>Plug-in per Firefox WPF  
 Il plug-in per Firefox WPF consente [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] e regime [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file per essere aperto ed eseguito al livello superiore o in un elemento IFRAME HTML nel browser Firefox. Un' [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] è un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione che può essere pubblicati in un server Web e avviata nel browser supportati. Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è un file XAML sola che può essere aperto e visualizzato nel browser supportati, molto simile a un file XML.  
  
 Il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plug-in per Firefox è installato con .NET Framework 3.5. Windows 7 include .NET Framework 3.5, ma non include il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plug-in per Firefox. Non è possibile installare il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plug-in per Firefox in Windows 7.  
  
 .NET Framework 4 non include il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plug-in per Firefox. Tuttavia, se sono installati sia .NET Framework 3.5 e .NET Framework 4, il plug-in per Firefox WPF viene installato con .NET Framework 3.5. Pertanto le applicazioni .NET Framework 4 verranno eseguito comunque perché l'Host WPF caricherà la versione corretta del framework. Per altre informazioni, vedere [Host WPF (PresentationHost.exe)](wpf-host-presentationhost-exe.md).  
  
## <a name="net-framework-assistant-for-firefox"></a>.NET Framework Assistant per Firefox  
 .NET Framework Assistant per Firefox Abilita autonomo di applicazioni ClickOnce per l'esecuzione dal browser Firefox. .NET Framework Assistant per Firefox funziona esattamente quando deve essere installata prima e dopo che il browser Firefox. Quando viene avviato il browser Firefox e [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] è installato, viene trovato e installa .NET Framework Assistant per Firefox. Gli utenti possono configurare .NET Framework Assistant per Firefox seguire questa procedura:  
  
- Chiedi conferma prima di eseguire l'applicazione ClickOnce.  
  
- Report tutte le versioni installate di .NET Framework o solo la versione più recente.  
  
 .NET Framework Assistant per Firefox è incluso con il [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]. Per informazioni sulla rimozione di .NET Framework Assistant per Firefox, vedere [come rimuovere .NET Framework Assistant per Firefox](https://go.microsoft.com/fwlink/?LinkId=177944).  
  
## <a name="see-also"></a>Vedere anche

- [Distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md)
- [Panoramica delle applicazioni browser XAML di WPF](wpf-xaml-browser-applications-overview.md)
- [Verificare se il plug-in delle applicazioni WPF per Firefox è installato](how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
