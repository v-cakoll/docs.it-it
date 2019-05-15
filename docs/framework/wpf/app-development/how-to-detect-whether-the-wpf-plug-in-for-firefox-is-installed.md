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
ms.openlocfilehash: 5ae2f39883c8edd7be912bfeb8326c14ca38704a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592615"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="cf7ab-102">Procedura: Verificare se il plug-in delle applicazioni WPF per Firefox è installato</span><span class="sxs-lookup"><span data-stu-id="cf7ab-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>

<span data-ttu-id="cf7ab-103">Consente a Windows Presentation Foundation (WPF) del plug-in per Firefox [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] e separare i file XAML per l'esecuzione nel browser Mozilla Firefox.</span><span class="sxs-lookup"><span data-stu-id="cf7ab-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="cf7ab-104">In questo argomento fornisce uno script scritto in HTML e JavaScript che gli amministratori possono utilizzare per determinare se è installato il plug-in per Firefox WPF.</span><span class="sxs-lookup"><span data-stu-id="cf7ab-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>

> [!NOTE]
> <span data-ttu-id="cf7ab-105">Per altre informazioni sull'installazione, distribuzione e il rilevamento di .NET Framework, vedere [installare .NET Framework per sviluppatori](../../install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="cf7ab-105">For more information about installing, deploying, and detecting the .NET Framework, see [Install the .NET Framework for developers](../../install/guide-for-developers.md).</span></span>

## <a name="example"></a><span data-ttu-id="cf7ab-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf7ab-106">Example</span></span>

<span data-ttu-id="cf7ab-107">Quando il [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] è installato, il computer client è configurato con un plug-in WPF per Firefox.</span><span class="sxs-lookup"><span data-stu-id="cf7ab-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="cf7ab-108">Lo script di esempio seguente controlla il plug-in WPF per Firefox e quindi visualizza un messaggio di stato appropriato.</span><span class="sxs-lookup"><span data-stu-id="cf7ab-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>

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

<span data-ttu-id="cf7ab-109">Se il controllo per il plug-in WPF per Firefox ha esito positivo, viene visualizzato il messaggio di stato seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf7ab-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is installed.`

<span data-ttu-id="cf7ab-110">In caso contrario, viene visualizzato il messaggio di stato seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf7ab-110">Otherwise, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a><span data-ttu-id="cf7ab-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf7ab-111">See also</span></span>

- [<span data-ttu-id="cf7ab-112">Verificare se .NET Framework 3.0 è installato</span><span class="sxs-lookup"><span data-stu-id="cf7ab-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [<span data-ttu-id="cf7ab-113">Verificare se .NET Framework 3.5 è installato</span><span class="sxs-lookup"><span data-stu-id="cf7ab-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [<span data-ttu-id="cf7ab-114">Panoramica delle applicazioni browser XAML di WPF</span><span class="sxs-lookup"><span data-stu-id="cf7ab-114">WPF XAML Browser Applications Overview</span></span>](wpf-xaml-browser-applications-overview.md)
