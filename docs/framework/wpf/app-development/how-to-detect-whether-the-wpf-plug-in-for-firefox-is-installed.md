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
ms.openlocfilehash: f84a0a2af43931b3ada1f674390ec5d841b79a1c
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690424"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>Procedura: Verificare se il plug-in delle applicazioni WPF per Firefox è installato

Consente a Windows Presentation Foundation (WPF) del plug-in per Firefox [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] e separare i file XAML per l'esecuzione nel browser Mozilla Firefox. In questo argomento fornisce uno script scritto in HTML e JavaScript che gli amministratori possono utilizzare per determinare se è installato il plug-in per Firefox WPF.

> [!NOTE]
> Per altre informazioni sull'installazione, distribuzione e il rilevamento di .NET Framework, vedere [installare .NET Framework per sviluppatori](../../install/guide-for-developers.md).

## <a name="example"></a>Esempio

Quando viene installato .NET Framework 3.5, il computer client è configurato con un plug-in WPF per Firefox. Lo script di esempio seguente controlla il plug-in WPF per Firefox e quindi visualizza un messaggio di stato appropriato.

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
