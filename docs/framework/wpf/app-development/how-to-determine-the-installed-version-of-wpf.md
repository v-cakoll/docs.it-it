---
title: Determinare la versione installata di WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: 8fc5c380779891b44b7c4f7f8aeb5ed119d8b768
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735690"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a><span data-ttu-id="b5eb1-102">Procedura: determinare la versione installata di WPF</span><span class="sxs-lookup"><span data-stu-id="b5eb1-102">How to: Determine the Installed Version of WPF</span></span>
<span data-ttu-id="b5eb1-103">Il numero di versione per la versione installata corrente di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] si trova nel **Registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="b5eb1-103">The version number for the current installed version of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is located in the **Registry**.</span></span>  
  
 <span data-ttu-id="b5eb1-104">Per trovare il numero di versione:</span><span class="sxs-lookup"><span data-stu-id="b5eb1-104">To find the version number:</span></span>  
  
1. <span data-ttu-id="b5eb1-105">Fare clic sul pulsante **Start** , quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="b5eb1-105">On the **Start** menu, click **Run**.</span></span>  
  
2. <span data-ttu-id="b5eb1-106">In **Apri**Digitare **Regedit. exe**.</span><span class="sxs-lookup"><span data-stu-id="b5eb1-106">In **Open**, type **regedit.exe**.</span></span>  
  
3. <span data-ttu-id="b5eb1-107">Aprire la chiave seguente:</span><span class="sxs-lookup"><span data-stu-id="b5eb1-107">Open the following key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 <span data-ttu-id="b5eb1-108">Il numero di versione del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene archiviato nel valore della **versione** .</span><span class="sxs-lookup"><span data-stu-id="b5eb1-108">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] version number is stored in the **Version** value.</span></span>
