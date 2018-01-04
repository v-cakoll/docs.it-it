---
title: "Stampa più protetta in Windows Form"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f36ee150e4dcca74141b644a55451abd4a4fd21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="more-secure-printing-in-windows-forms"></a><span data-ttu-id="a22b1-102">Stampa più protetta in Windows Form</span><span class="sxs-lookup"><span data-stu-id="a22b1-102">More Secure Printing in Windows Forms</span></span>
<span data-ttu-id="a22b1-103">Applicazioni Windows Forms includono spesso funzionalità di stampa.</span><span class="sxs-lookup"><span data-stu-id="a22b1-103">Windows Forms applications frequently include printing abilities.</span></span> <span data-ttu-id="a22b1-104">Il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] utilizza il <xref:System.Drawing.Printing.PrintingPermission> classe per controllare l'accesso alle funzionalità di stampa e associato <xref:System.Drawing.Printing.PrintingPermissionLevel> il valore di enumerazione per indicare il livello di accesso.</span><span class="sxs-lookup"><span data-stu-id="a22b1-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] uses the <xref:System.Drawing.Printing.PrintingPermission> class to control access to printing capabilities and the associated <xref:System.Drawing.Printing.PrintingPermissionLevel> enumeration value to indicate the level of access.</span></span> <span data-ttu-id="a22b1-105">Per impostazione predefinita, la stampa è abilitata per impostazione predefinita nelle aree Internet e Intranet locale; Tuttavia, il livello di accesso è limitato in entrambe le aree.</span><span class="sxs-lookup"><span data-stu-id="a22b1-105">By default, printing is enabled by default in the Local Intranet and Internet zones; however, the level of access is restricted in both zones.</span></span> <span data-ttu-id="a22b1-106">Se l'applicazione può essere stampato, è necessario l'intervento dell'utente, o non stampa dipende dal valore di autorizzazione concesso all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a22b1-106">Whether your application can print, requires user interaction, or cannot print depends upon the permission value granted to the application.</span></span> <span data-ttu-id="a22b1-107">Per impostazione predefinita, l'area Intranet locale riceve <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> accesso e l'area Intranet riceve <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> accesso.</span><span class="sxs-lookup"><span data-stu-id="a22b1-107">By default, the Local Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> access and the Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> access.</span></span>  
  
 <span data-ttu-id="a22b1-108">La tabella seguente illustra le funzionalità disponibili per ogni livello di autorizzazione di stampa.</span><span class="sxs-lookup"><span data-stu-id="a22b1-108">The following table shows the functionality available at each printing permission level.</span></span>  
  
|<span data-ttu-id="a22b1-109">PrintingPermissionLevel</span><span class="sxs-lookup"><span data-stu-id="a22b1-109">PrintingPermissionLevel</span></span>|<span data-ttu-id="a22b1-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a22b1-110">Description</span></span>|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|<span data-ttu-id="a22b1-111">Fornisce accesso completo a tutte le stampanti installate.</span><span class="sxs-lookup"><span data-stu-id="a22b1-111">Provides full access to all installed printers.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|<span data-ttu-id="a22b1-112">Consente la stampa a livello di codice per la stampante predefinita e stampa protetta mediante una finestra di dialogo di stampa limitata.</span><span class="sxs-lookup"><span data-stu-id="a22b1-112">Enables programmatic printing to the default printer and safer printing through a restrictive printing dialog box.</span></span> <span data-ttu-id="a22b1-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> è un subset di <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span><span class="sxs-lookup"><span data-stu-id="a22b1-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|<span data-ttu-id="a22b1-114">Consente la stampa solo da una finestra di dialogo più limitata.</span><span class="sxs-lookup"><span data-stu-id="a22b1-114">Provides printing only from a more-restricted dialog box.</span></span> <span data-ttu-id="a22b1-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> è un subset di <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span><span class="sxs-lookup"><span data-stu-id="a22b1-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|<span data-ttu-id="a22b1-116">Impedisce l'accesso alle stampanti.</span><span class="sxs-lookup"><span data-stu-id="a22b1-116">Prevents access to printers.</span></span> <span data-ttu-id="a22b1-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> è un subset di <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span><span class="sxs-lookup"><span data-stu-id="a22b1-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a22b1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a22b1-118">See Also</span></span>  
 [<span data-ttu-id="a22b1-119">Accesso più sicuro a file e dati in Windows Form</span><span class="sxs-lookup"><span data-stu-id="a22b1-119">More Secure File and Data Access in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 [<span data-ttu-id="a22b1-120">Considerazioni aggiuntive sulla sicurezza in Windows Form</span><span class="sxs-lookup"><span data-stu-id="a22b1-120">Additional Security Considerations in Windows Forms</span></span>](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 [<span data-ttu-id="a22b1-121">Panoramica della sicurezza in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a22b1-121">Security in Windows Forms Overview</span></span>](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [<span data-ttu-id="a22b1-122">Sicurezza di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a22b1-122">Windows Forms Security</span></span>](../../../docs/framework/winforms/windows-forms-security.md)
