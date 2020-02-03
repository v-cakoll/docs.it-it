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
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="398ac-102">Procedura: rilevare se il plug-in WPF per Firefox è installato o meno</span><span class="sxs-lookup"><span data-stu-id="398ac-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>

<span data-ttu-id="398ac-103">Il plug-in Windows Presentation Foundation (WPF) per Firefox consente le applicazioni browser XAML (XBAP) e i file XAML separati per l'esecuzione nel browser Mozilla Firefox.</span><span class="sxs-lookup"><span data-stu-id="398ac-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables XAML browser applications (XBAPs) and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="398ac-104">In questo argomento viene fornito uno script scritto in HTML e JavaScript che gli amministratori possono utilizzare per determinare se il plug-in WPF per Firefox è installato.</span><span class="sxs-lookup"><span data-stu-id="398ac-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>

> [!NOTE]
> <span data-ttu-id="398ac-105">Per ulteriori informazioni sull'installazione, la distribuzione e il rilevamento del .NET Framework, vedere [Install the .NET Framework for Developers](../../install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="398ac-105">For more information about installing, deploying, and detecting the .NET Framework, see [Install the .NET Framework for developers](../../install/guide-for-developers.md).</span></span>

## <a name="example"></a><span data-ttu-id="398ac-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="398ac-106">Example</span></span>

<span data-ttu-id="398ac-107">Quando viene installato il .NET Framework 3,5, il computer client viene configurato con un plug-in WPF per Firefox.</span><span class="sxs-lookup"><span data-stu-id="398ac-107">When the .NET Framework 3.5 is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="398ac-108">Nello script di esempio seguente viene verificato il plug-in WPF per Firefox, quindi viene visualizzato un messaggio di stato appropriato.</span><span class="sxs-lookup"><span data-stu-id="398ac-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>

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

<span data-ttu-id="398ac-109">Se il controllo per il plug-in WPF per Firefox ha esito positivo, viene visualizzato il messaggio di stato seguente:</span><span class="sxs-lookup"><span data-stu-id="398ac-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is installed.`

<span data-ttu-id="398ac-110">In caso contrario, viene visualizzato il messaggio di stato seguente:</span><span class="sxs-lookup"><span data-stu-id="398ac-110">Otherwise, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a><span data-ttu-id="398ac-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="398ac-111">See also</span></span>

- [<span data-ttu-id="398ac-112">Verificare se .NET Framework 3.0 è installato</span><span class="sxs-lookup"><span data-stu-id="398ac-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [<span data-ttu-id="398ac-113">Verificare se .NET Framework 3.5 è installato</span><span class="sxs-lookup"><span data-stu-id="398ac-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [<span data-ttu-id="398ac-114">Panoramica delle applicazioni browser XAML di WPF</span><span class="sxs-lookup"><span data-stu-id="398ac-114">WPF XAML Browser Applications Overview</span></span>](wpf-xaml-browser-applications-overview.md)
