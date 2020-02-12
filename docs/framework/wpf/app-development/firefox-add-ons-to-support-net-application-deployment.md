---
title: Componenti aggiuntivi di Firefox per supportare la distribuzione di applicazioni .NET
ms.date: 03/30/2017
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
ms.openlocfilehash: 56f5f633092d8aa0bfabdb0570ec26f14221838d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124611"
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>Componenti aggiuntivi di Firefox per supportare la distribuzione di applicazioni .NET
Il plug-in Windows Presentation Foundation (WPF) per Firefox e il .NET Framework Assistant per Firefox abilitano le applicazioni browser XAML (XBAPs), le [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Loose e le applicazioni ClickOnce per l'uso con il browser Mozilla Firefox.  
  
## <a name="wpf-plug-in-for-firefox"></a>Plug-in WPF per Firefox  
 Il plug-in WPF per Firefox consente l'esplorazione e l'esecuzione delle applicazioni XBAP e dei file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separati in un IFRAME HTML del browser Firefox. Un'applicazione XBAP è un'applicazione WPF che può essere pubblicata su un server Web e avviata all'interno di browser supportati. Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è un file solo XAML che è possibile esplorare e visualizzare nei browser supportati, molto simile a un file XML.  
  
 Il plug-in WPF per Firefox viene installato con il .NET Framework 3,5. La finestra 7 include il .NET Framework 3,5, ma non include il plug-in WPF per Firefox. Non è possibile installare il plug-in WPF per Firefox in Windows 7.  
  
 Il .NET Framework 4 non include il plug-in WPF per Firefox. Tuttavia, se sono installati sia la .NET Framework 3,5 che la .NET Framework 4, il plug-in WPF per Firefox viene installato con il .NET Framework 3,5. Pertanto .NET Framework 4 applicazioni vengono comunque eseguite perché l'host WPF caricherà la versione corretta del Framework. Per ulteriori informazioni, vedere [host WPF (PresentationHost. exe)](wpf-host-presentationhost-exe.md).  
  
## <a name="net-framework-assistant-for-firefox"></a>.NET Framework Assistant per Firefox  
 Il .NET Framework Assistant per Firefox consente l'esecuzione di applicazioni ClickOnce autonome dal browser Firefox. Il .NET Framework Assistant per Firefox funziona in modo identico quando viene installato prima e dopo il browser Firefox. Quando viene avviato il browser Firefox e viene installato il .NET Framework 3,5 SP1, Firefox trova e installa il .NET Framework Assistant per Firefox. Gli utenti possono configurare .NET Framework Assistant per Firefox per eseguire le operazioni seguenti:  
  
- Chiedi conferma prima di eseguire l'applicazione ClickOnce.  
  
- Segnala tutte le versioni installate del .NET Framework o solo la versione più recente.  
  
 Il .NET Framework Assistant per Firefox è incluso nella .NET Framework 3,5 SP1. Per informazioni sulla rimozione di .NET Framework Assistant per Firefox, vedere [How to Remove the .NET Framework Assistant for Firefox](https://support.microsoft.com/help/963707/how-to-remove-the-net-framework-assistant-for-firefox).  
  
## <a name="see-also"></a>Vedere anche

- [Distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md)
- [Panoramica delle applicazioni browser XAML di WPF](wpf-xaml-browser-applications-overview.md)
- [Verificare se il plug-in delle applicazioni WPF per Firefox è installato](how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
