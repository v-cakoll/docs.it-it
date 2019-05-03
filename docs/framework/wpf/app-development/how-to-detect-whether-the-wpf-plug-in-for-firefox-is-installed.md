---
title: 'Procedura: Verificare se il plug-in delle applicazioni WPF per Firefox è installato'
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: 138c212e79654b8ac875628692b49bb6a38cb695
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947875"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>Procedura: Verificare se il plug-in delle applicazioni WPF per Firefox è installato

Consente a Windows Presentation Foundation (WPF) del plug-in per Firefox [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] e separare i file XAML per l'esecuzione nel browser Mozilla Firefox. In questo argomento fornisce uno script scritto in HTML e JavaScript che gli amministratori possono utilizzare per determinare se è installato il plug-in per Firefox WPF.

> [!NOTE]
> Per altre informazioni sull'installazione, la distribuzione e rilevare il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], vedere [installare .NET Framework per sviluppatori](../../install/guide-for-developers.md).

## <a name="example"></a>Esempio

Quando il [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] è installato, il computer client è configurato con un plug-in WPF per Firefox. Lo script di esempio seguente controlla il plug-in WPF per Firefox e quindi visualizza un messaggio di stato appropriato.

```html
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

- [Verificare se .NET Framework 3.0 è installato](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [Verificare se .NET Framework 3.5 è installato](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [Panoramica delle applicazioni browser XAML di WPF](wpf-xaml-browser-applications-overview.md)
