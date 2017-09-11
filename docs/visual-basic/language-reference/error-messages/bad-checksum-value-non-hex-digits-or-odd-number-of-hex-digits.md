---
title: Valore checksum non valido, le cifre esadecimali non o un numero dispari di cifre esadecimali | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42033
- vbc42033
dev_langs:
- VB
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 70a8fc5e0200c15858ad1288e12b2aeb1e5303d8
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a><span data-ttu-id="7d6b6-102">Valore checksum non valido. Cifre esadecimali non presenti o in numero dispari</span><span class="sxs-lookup"><span data-stu-id="7d6b6-102">Bad checksum value, non hex digits or odd number of hex digits</span></span>
<span data-ttu-id="7d6b6-103">Un valore di checksum include cifre esadecimali non valide o un numero di cifre dispari.</span><span class="sxs-lookup"><span data-stu-id="7d6b6-103">A checksum value contains invalid hexadecimal digits or has an odd number of digits.</span></span>  
  
 <span data-ttu-id="7d6b6-104">Quando ASP.NET genera un file di origine Visual Basic, con estensione vb, calcola un checksum e lo colloca in un file di origine nascosto identificato da `#externalchecksum`.</span><span class="sxs-lookup"><span data-stu-id="7d6b6-104">When ASP.NET generates a Visual Basic source file (extension .vb), it calculates a checksum and places it in a hidden source file identified by `#externalchecksum`.</span></span> <span data-ttu-id="7d6b6-105">Anche un utente può generare un file con estensione vb per lo stesso scopo, ma questo processo è più adatto per essere usato internamente.</span><span class="sxs-lookup"><span data-stu-id="7d6b6-105">It is possible for a user generating a .vb file to do this also, but this process is best left to internal use.</span></span>  
  
 <span data-ttu-id="7d6b6-106">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="7d6b6-106">By default, this message is a warning.</span></span> <span data-ttu-id="7d6b6-107">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="7d6b6-107">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="7d6b6-108">**ID errore:** BC42033</span><span class="sxs-lookup"><span data-stu-id="7d6b6-108">**Error ID:** BC42033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7d6b6-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7d6b6-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="7d6b6-110">Se il file di origine Visual Basic viene generato da ASP.NET, riavviare la compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="7d6b6-110">If ASP.NET is generating the Visual Basic source file, restart the project build.</span></span>  
  
2.  <span data-ttu-id="7d6b6-111">Se l'avviso persiste dopo il riavvio, reinstallare ASP.NET e riprovare a eseguire la compilazione.</span><span class="sxs-lookup"><span data-stu-id="7d6b6-111">If this warning persists after restarting, reinstall ASP.NET and try the build again.</span></span>  
  
3.  <span data-ttu-id="7d6b6-112">Se l'avviso persiste ancora o non si usa ASP.NET, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7d6b6-112">If the warning still persists, or if you are not using ASP.NET, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d6b6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d6b6-113">See Also</span></span>  
 <span data-ttu-id="7d6b6-114">[Panoramica di ASP.NET](https://msdn.microsoft.com/library/4w3ex9c2.aspx) </span><span class="sxs-lookup"><span data-stu-id="7d6b6-114">[ASP.NET Overview](https://msdn.microsoft.com/library/4w3ex9c2.aspx) </span></span>  
<span data-ttu-id="7d6b6-115"> [Comunicazioni con Microsoft](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="7d6b6-115"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
