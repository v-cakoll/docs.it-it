---
title: "Procedura: verificare se .NET Framework 3.0 è installato"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WinFX Runtime user-agent string
- presence of WPT [WPF], detecting
- detecting WPF presence [WPF]
ms.assetid: 7f71d652-1749-4379-945a-aa2e3994cb43
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e013c9426507e20da05df26932a1f9cf1e5df761
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-detect-whether-the-net-framework-30-is-installed"></a>Procedura: verificare se .NET Framework 3.0 è installato
Prima che gli amministratori possono distribuire [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] applicazioni in un sistema, devono confermare che il [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] del runtime. In questo argomento viene fornito uno script HTML/JavaScript che gli amministratori possono utilizzare per determinare se [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] è presente in un sistema.  
  
> [!NOTE]
>  Per ulteriori informazioni sull'installazione, distribuzione e il rilevamento di [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], vedere la discussione nella [distribuzione di Microsoft .NET Framework versione 3.0](http://go.microsoft.com/fwlink/?LinkId=96739).  
  
<a name="content_expiration"></a>   
## <a name="detect-the-net-clr-user-agent-string"></a>Individuare la stringa User-Agent ".NET CLR"  
 Quando [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] è installato, il file MSI aggiunge ".NET CLR" e il numero di versione per la stringa agente utente. Nell'esempio seguente viene illustrato uno script incorporato in una semplice pagina HTML. Lo script cerca nella stringa agente utente per determinare se [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] sia installato e viene visualizzato un messaggio di stato ai risultati della ricerca.  
  
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
  
 Se la ricerca per la versione ".NET CLR" ha esito positivo, viene visualizzato il seguente tipo di messaggio di stato:  
  
 `This machine has the correct version of the .NET Framework 3.0: 3.0.04425.00`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727; .NET CLR 3.0.04425.00).`  
  
 In caso contrario, viene visualizzato il seguente tipo di messaggio di stato:  
  
 `This machine does not have correct version of the .NET Framework 3.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727).`
