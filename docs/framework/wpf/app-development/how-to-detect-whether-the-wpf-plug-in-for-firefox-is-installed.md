---
title: 'Procedura: rilevare se il plug-in WPF per Firefox è installato o meno'
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: ba411d662a8e5b0c4727e23c8d507e8924b6e9e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>Procedura: rilevare se il plug-in WPF per Firefox è installato o meno
Consente a Windows Presentation Foundation (WPF) plug-in per Firefox [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] e separare i file XAML in esecuzione nel browser Mozilla Firefox. In questo argomento fornisce uno script scritto in HTML e JavaScript che gli amministratori possono utilizzare per determinare se è installato il plug-in per Firefox WPF.  
  
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
