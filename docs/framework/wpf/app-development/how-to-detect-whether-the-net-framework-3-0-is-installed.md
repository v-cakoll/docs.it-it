---
title: 'Procedura: verificare se .NET Framework 3.0 è installato'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WinFX Runtime user-agent string
- presence of WPT [WPF], detecting
- detecting WPF presence [WPF]
ms.assetid: 7f71d652-1749-4379-945a-aa2e3994cb43
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 48295a187870340948b045a64b852f1e6fdc1a65
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-detect-whether-the-net-framework-30-is-installed"></a><span data-ttu-id="11bb3-102">Procedura: verificare se .NET Framework 3.0 è installato</span><span class="sxs-lookup"><span data-stu-id="11bb3-102">How to: Detect Whether the .NET Framework 3.0 Is Installed</span></span>
<span data-ttu-id="11bb3-103">Prima che gli amministratori possono distribuire [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] applicazioni in un sistema, devono confermare che il [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] del runtime.</span><span class="sxs-lookup"><span data-stu-id="11bb3-103">Before administrators can deploy [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] applications on a system, they must first confirm that the [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] runtime is present.</span></span> <span data-ttu-id="11bb3-104">In questo argomento viene fornito uno script HTML/JavaScript che gli amministratori possono utilizzare per determinare se [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] è presente in un sistema.</span><span class="sxs-lookup"><span data-stu-id="11bb3-104">This topic provides a script written in HTML/JavaScript that administrators can use to determine whether [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] is present on a system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11bb3-105">Per ulteriori informazioni sull'installazione, distribuzione e il rilevamento di Microsoft .NET Framework, vedere la discussione nella [distribuzione di Microsoft .NET Framework versione 3.0](http://go.microsoft.com/fwlink/?LinkId=96739).</span><span class="sxs-lookup"><span data-stu-id="11bb3-105">For more detailed information on installing, deploying, and detecting the Microsoft .NET Framework, see the discussion in [Deploying Microsoft .NET Framework Version 3.0](http://go.microsoft.com/fwlink/?LinkId=96739).</span></span>  
  
<a name="content_expiration"></a>   
## <a name="detect-the-net-clr-user-agent-string"></a><span data-ttu-id="11bb3-106">Individuare la stringa User-Agent ".NET CLR"</span><span class="sxs-lookup"><span data-stu-id="11bb3-106">Detect the ".NET CLR" User-Agent String</span></span>  
 <span data-ttu-id="11bb3-107">Quando [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] è installato, il file MSI aggiunge ".NET CLR" e il numero di versione per la stringa agente utente.</span><span class="sxs-lookup"><span data-stu-id="11bb3-107">When [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] is installed, the MSI adds ".NET CLR" and the version number to the UserAgent string.</span></span> <span data-ttu-id="11bb3-108">Nell'esempio seguente viene illustrato uno script incorporato in una semplice pagina HTML.</span><span class="sxs-lookup"><span data-stu-id="11bb3-108">The following example shows a script embedded in a simple HTML page.</span></span> <span data-ttu-id="11bb3-109">Lo script cerca nella stringa agente utente per determinare se [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] sia installato e viene visualizzato un messaggio di stato ai risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="11bb3-109">The script searches the UserAgent string to determine whether [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] is installed, and displays a status message on the results of the search.</span></span>  
  
```  
<HTML>  
  <HEAD>  
    <TITLE>Test for the .NET Framework 3.0</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT LANGUAGE="JavaScript">  
    <!--  
    var dotNETRuntimeVersion = "3.0.04425.00";  
  
    function window::onload()  
    {  
      if (HasRuntimeVersion(dotNETRuntimeVersion))  
      {  
        result.innerText =   
          "This machine has the correct version of the .NET Framework 3.0: "   
          + dotNETRuntimeVersion  
      }   
      else  
      {  
        result.innerText =   
          "This machine does not have the correct version of the .NET Framework 3.0."  
      }  
      result.innerText += "\n\nThis machine's userAgent string is: " +   
        navigator.userAgent + ".";  
    }  
  
    //  
    // Retrieve the version from the user agent string and   
    // compare with the specified version.  
    //  
    function HasRuntimeVersion(versionToCheck)  
    {  
      var userAgentString =   
        navigator.userAgent.match(/.NET CLR [0-9.]+/g);  
  
      if (userAgentString != null)  
      {  
        var i;  
  
        for (i = 0; i < userAgentString.length; ++i)  
        {  
          if (CompareVersions(GetVersion(versionToCheck),   
            GetVersion(userAgentString[i])) <= 0)  
            return true;  
        }  
      }  
  
      return false;  
    }  
  
    //  
    // Extract the numeric part of the version string.  
    //  
    function GetVersion(versionString)  
    {  
      var numericString =   
        versionString.match(/([0-9]+)\.([0-9]+)\.([0-9]+)/i);  
      return numericString.slice(1);  
    }  
  
    //  
    // Compare the 2 version strings by converting them to numeric format.  
    //  
    function CompareVersions(version1, version2)  
    {  
      for (i = 0; i < version1.length; ++i)  
      {  
        var number1 = new Number(version1[i]);  
        var number2 = new Number(version2[i]);  
  
        if (number1 < number2)  
          return -1;  
  
        if (number1 > number2)  
          return 1;  
      }  
  
      return 0;  
    }  
  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY>  
    <div id="result" />  
  </BODY>  
</HTML>  
```  
  
 <span data-ttu-id="11bb3-110">Se la ricerca per la versione ".NET CLR" ha esito positivo, viene visualizzato il seguente tipo di messaggio di stato:</span><span class="sxs-lookup"><span data-stu-id="11bb3-110">If the search for the ".NET CLR " version is successful, the following type of status message appears:</span></span>  
  
 `This machine has the correct version of the .NET Framework 3.0: 3.0.04425.00`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727; .NET CLR 3.0.04425.00).`  
  
 <span data-ttu-id="11bb3-111">In caso contrario, viene visualizzato il seguente tipo di messaggio di stato:</span><span class="sxs-lookup"><span data-stu-id="11bb3-111">Otherwise, the following type of status message appears:</span></span>  
  
 `This machine does not have correct version of the .NET Framework 3.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727).`
