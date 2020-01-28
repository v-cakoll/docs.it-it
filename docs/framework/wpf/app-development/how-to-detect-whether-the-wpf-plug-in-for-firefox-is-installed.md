---
title: Rilevare se è installato il plug-in WPF per Firefox
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: 91680859c1742e5d5443d626c81273a80504f4a8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740393"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>Procedura: rilevare se il plug-in WPF per Firefox è installato o meno

Il plug-in Windows Presentation Foundation (WPF) per Firefox consente le applicazioni browser XAML (XBAP) e i file XAML separati per l'esecuzione nel browser Mozilla Firefox. In questo argomento viene fornito uno script scritto in HTML e JavaScript che gli amministratori possono utilizzare per determinare se il plug-in WPF per Firefox è installato.

> [!NOTE]
> Per ulteriori informazioni sull'installazione, la distribuzione e il rilevamento del .NET Framework, vedere [Install the .NET Framework for Developers](../../install/guide-for-developers.md).

## <a name="example"></a>Esempio

Quando viene installato il .NET Framework 3,5, il computer client viene configurato con un plug-in WPF per Firefox. Nello script di esempio seguente viene verificato il plug-in WPF per Firefox, quindi viene visualizzato un messaggio di stato appropriato.

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

Se il controllo per il plug-in WPF per Firefox ha esito positivo, viene visualizzato il messaggio di stato seguente:

`The WPF plug-in for Firefox is installed.`

In caso contrario, viene visualizzato il messaggio di stato seguente:

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a>Vedere anche

- [Verificare se .NET Framework 3.0 è installato](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [Verificare se .NET Framework 3.5 è installato](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [Panoramica delle applicazioni browser XAML di WPF](wpf-xaml-browser-applications-overview.md)
