---
title: Valore checksum non valido. Cifre esadecimali non presenti o in numero dispari
ms.date: 07/20/2015
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
ms.openlocfilehash: e682c2c23dd6fe80aee87d2a86b3df2dae66b802
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213078"
---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a><span data-ttu-id="9dddc-102">Valore checksum non valido. Cifre esadecimali non presenti o in numero dispari</span><span class="sxs-lookup"><span data-stu-id="9dddc-102">Bad checksum value, non hex digits or odd number of hex digits</span></span>
<span data-ttu-id="9dddc-103">Un valore di checksum include cifre esadecimali non valide o un numero di cifre dispari.</span><span class="sxs-lookup"><span data-stu-id="9dddc-103">A checksum value contains invalid hexadecimal digits or has an odd number of digits.</span></span>  
  
 <span data-ttu-id="9dddc-104">Quando ASP.NET genera un file di origine Visual Basic, con estensione vb, calcola un checksum e lo colloca in un file di origine nascosto identificato da `#externalchecksum`.</span><span class="sxs-lookup"><span data-stu-id="9dddc-104">When ASP.NET generates a Visual Basic source file (extension .vb), it calculates a checksum and places it in a hidden source file identified by `#externalchecksum`.</span></span> <span data-ttu-id="9dddc-105">Anche un utente può generare un file con estensione vb per lo stesso scopo, ma questo processo è più adatto per essere usato internamente.</span><span class="sxs-lookup"><span data-stu-id="9dddc-105">It is possible for a user generating a .vb file to do this also, but this process is best left to internal use.</span></span>  
  
 <span data-ttu-id="9dddc-106">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="9dddc-106">By default, this message is a warning.</span></span> <span data-ttu-id="9dddc-107">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="9dddc-107">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="9dddc-108">**ID errore:** BC42033</span><span class="sxs-lookup"><span data-stu-id="9dddc-108">**Error ID:** BC42033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9dddc-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="9dddc-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="9dddc-110">Se il file di origine Visual Basic viene generato da ASP.NET, riavviare la compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="9dddc-110">If ASP.NET is generating the Visual Basic source file, restart the project build.</span></span>  
  
2.  <span data-ttu-id="9dddc-111">Se l'avviso persiste dopo il riavvio, reinstallare ASP.NET e riprovare a eseguire la compilazione.</span><span class="sxs-lookup"><span data-stu-id="9dddc-111">If this warning persists after restarting, reinstall ASP.NET and try the build again.</span></span>  
  
3.  <span data-ttu-id="9dddc-112">Se l'avviso persiste ancora o non si usa ASP.NET, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9dddc-112">If the warning still persists, or if you are not using ASP.NET, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dddc-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9dddc-113">See also</span></span>

- [<span data-ttu-id="9dddc-114">Panoramica di ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9dddc-114">ASP.NET Overview</span></span>](/aspnet/overview)  
- <span data-ttu-id="9dddc-115">[Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)</span><span class="sxs-lookup"><span data-stu-id="9dddc-115">[Talk to Us](/visualstudio/ide/talk-to-us)</span></span>
