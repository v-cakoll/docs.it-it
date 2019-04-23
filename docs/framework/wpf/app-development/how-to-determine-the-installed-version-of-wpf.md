---
title: 'Procedura: Determinare la versione installata di WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: ffbd9a4c7f66dff9c8773dff4259551e20aa963d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768020"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a><span data-ttu-id="589fc-102">Procedura: Determinare la versione installata di WPF</span><span class="sxs-lookup"><span data-stu-id="589fc-102">How to: Determine the Installed Version of WPF</span></span>
<span data-ttu-id="589fc-103">Il numero di versione per la versione attualmente installata di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] si trova nel **registro**.</span><span class="sxs-lookup"><span data-stu-id="589fc-103">The version number for the current installed version of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is located in the **Registry**.</span></span>  
  
 <span data-ttu-id="589fc-104">Per trovare il numero di versione:</span><span class="sxs-lookup"><span data-stu-id="589fc-104">To find the version number:</span></span>  
  
1. <span data-ttu-id="589fc-105">Fare clic sul pulsante **Start** , quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="589fc-105">On the **Start** menu, click **Run**.</span></span>  
  
2. <span data-ttu-id="589fc-106">Nelle **aperto**, digitare **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="589fc-106">In **Open**, type **regedit.exe**.</span></span>  
  
3. <span data-ttu-id="589fc-107">Aprire la chiave seguente:</span><span class="sxs-lookup"><span data-stu-id="589fc-107">Open the following key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 <span data-ttu-id="589fc-108">Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] numero di versione viene archiviato nel **versione** valore.</span><span class="sxs-lookup"><span data-stu-id="589fc-108">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] version number is stored in the **Version** value.</span></span>
