---
title: "Procedura: rilevare se il plug-in WPF per Firefox è installato o meno"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3012afc118420a83c869785d26c28f1eee969cb3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>Procedura: rilevare se il plug-in WPF per Firefox è installato o meno
Il [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] plug-in per Firefox consente [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] e separare i file XAML in esecuzione nel browser Mozilla Firefox. In questo argomento fornisce uno script scritto in HTML e JavaScript che gli amministratori possono utilizzare per determinare se è installato il plug-in per Firefox WPF.  
  
> [!NOTE]
>  Per ulteriori informazioni sull'installazione, distribuzione e il rilevamento di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], vedere [installare .NET Framework per sviluppatori](../../../../docs/framework/install/guide-for-developers.md).  
  
## <a name="example"></a>Esempio  
 Quando il [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] è installato, il computer client è configurato con un plug-in WPF per Firefox. Lo script di esempio seguente controlla il plug-in WPF per Firefox e verrà visualizzato un messaggio di stato appropriato.  
  
```  
<HTML>  
  
  <HEAD>  
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT type="text/javascript">  
    <!--  
    function OnLoad()  
    {  
  
       // Check for the WPF plug-in for Firefox and report  
       var msg = "The WPF plug-in for Firefox is ";  
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];  
       if( wpfPlugin != null ) {  
          document.writeln(msg + " installed.");  
       }  
       else {  
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");  
       }  
    }  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY onload="OnLoad()" />  
  
</HTML>  
```  
  
 Se il controllo per il plug-in WPF per Firefox ha esito positivo, viene visualizzato il messaggio di stato seguenti:  
  
 `The WPF plug-in for Firefox is installed.`  
  
 In caso contrario, viene visualizzato il messaggio di stato seguenti:  
  
 `The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`  
  
## <a name="see-also"></a>Vedere anche  
 [Verificare se .NET Framework 3.0 è installato](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)  
 [Verificare se .NET Framework 3.5 è installato](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)  
 [Panoramica delle applicazioni browser XAML di WPF](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)
