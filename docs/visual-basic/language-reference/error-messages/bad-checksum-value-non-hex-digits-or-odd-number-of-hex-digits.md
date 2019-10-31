---
title: Valore checksum non valido. Cifre esadecimali non presenti o in numero dispari
ms.date: 07/20/2015
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
ms.openlocfilehash: 1ae4113505ca63df9b20e6e71aa0b418da4ef924
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197343"
---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a><span data-ttu-id="3ebf9-102">Valore checksum non valido. Cifre esadecimali non presenti o in numero dispari</span><span class="sxs-lookup"><span data-stu-id="3ebf9-102">Bad checksum value, non hex digits or odd number of hex digits</span></span>
<span data-ttu-id="3ebf9-103">Un valore di checksum include cifre esadecimali non valide o un numero di cifre dispari.</span><span class="sxs-lookup"><span data-stu-id="3ebf9-103">A checksum value contains invalid hexadecimal digits or has an odd number of digits.</span></span>  
  
 <span data-ttu-id="3ebf9-104">Quando ASP.NET genera un file di origine Visual Basic, con estensione vb, calcola un checksum e lo colloca in un file di origine nascosto identificato da `#externalchecksum`.</span><span class="sxs-lookup"><span data-stu-id="3ebf9-104">When ASP.NET generates a Visual Basic source file (extension .vb), it calculates a checksum and places it in a hidden source file identified by `#externalchecksum`.</span></span> <span data-ttu-id="3ebf9-105">Anche un utente può generare un file con estensione vb per lo stesso scopo, ma questo processo è più adatto per essere usato internamente.</span><span class="sxs-lookup"><span data-stu-id="3ebf9-105">It is possible for a user generating a .vb file to do this also, but this process is best left to internal use.</span></span>  
  
 <span data-ttu-id="3ebf9-106">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="3ebf9-106">By default, this message is a warning.</span></span> <span data-ttu-id="3ebf9-107">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="3ebf9-107">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="3ebf9-108">**ID errore:** BC42033</span><span class="sxs-lookup"><span data-stu-id="3ebf9-108">**Error ID:** BC42033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3ebf9-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="3ebf9-109">To correct this error</span></span>  
  
1. <span data-ttu-id="3ebf9-110">Se il file di origine Visual Basic viene generato da ASP.NET, riavviare la compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="3ebf9-110">If ASP.NET is generating the Visual Basic source file, restart the project build.</span></span>  
  
2. <span data-ttu-id="3ebf9-111">Se l'avviso persiste dopo il riavvio, reinstallare ASP.NET e riprovare a eseguire la compilazione.</span><span class="sxs-lookup"><span data-stu-id="3ebf9-111">If this warning persists after restarting, reinstall ASP.NET and try the build again.</span></span>  
  
3. <span data-ttu-id="3ebf9-112">Se l'avviso persiste ancora o non si usa ASP.NET, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ebf9-112">If the warning still persists, or if you are not using ASP.NET, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ebf9-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ebf9-113">See also</span></span>

- [<span data-ttu-id="3ebf9-114">Panoramica di ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3ebf9-114">ASP.NET Overview</span></span>](/aspnet/overview)
- <span data-ttu-id="3ebf9-115">[Talk to Us](/visualstudio/ide/feedback-options) (Comunicazioni con Microsoft)</span><span class="sxs-lookup"><span data-stu-id="3ebf9-115">[Talk to Us](/visualstudio/ide/feedback-options)</span></span>
