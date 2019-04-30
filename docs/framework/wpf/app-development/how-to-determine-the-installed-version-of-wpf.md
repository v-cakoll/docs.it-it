---
title: 'Procedura: Determinare la versione installata di WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: ffbd9a4c7f66dff9c8773dff4259551e20aa963d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052456"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a><span data-ttu-id="e457c-102">Procedura: Determinare la versione installata di WPF</span><span class="sxs-lookup"><span data-stu-id="e457c-102">How to: Determine the Installed Version of WPF</span></span>
<span data-ttu-id="e457c-103">Il numero di versione per la versione attualmente installata di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] si trova nel **registro**.</span><span class="sxs-lookup"><span data-stu-id="e457c-103">The version number for the current installed version of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is located in the **Registry**.</span></span>  
  
 <span data-ttu-id="e457c-104">Per trovare il numero di versione:</span><span class="sxs-lookup"><span data-stu-id="e457c-104">To find the version number:</span></span>  
  
1. <span data-ttu-id="e457c-105">Fare clic sul pulsante **Start** , quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e457c-105">On the **Start** menu, click **Run**.</span></span>  
  
2. <span data-ttu-id="e457c-106">Nelle **aperto**, digitare **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="e457c-106">In **Open**, type **regedit.exe**.</span></span>  
  
3. <span data-ttu-id="e457c-107">Aprire la chiave seguente:</span><span class="sxs-lookup"><span data-stu-id="e457c-107">Open the following key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 <span data-ttu-id="e457c-108">Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] numero di versione viene archiviato nel **versione** valore.</span><span class="sxs-lookup"><span data-stu-id="e457c-108">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] version number is stored in the **Version** value.</span></span>
