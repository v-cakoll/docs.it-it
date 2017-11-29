---
title: Globalizzazione di Windows Form e codifica
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView control [Windows Forms], lack of Unicode support
- DateTimePicker control [Windows Forms], lack of Unicode support
- TrackBar control [Windows Forms], lack of Unicode support
- ImageList component [Windows Forms], lack of Unicode support
- Unicode [Windows Forms]
- ToolBar control [Windows Forms], lack of Unicode support
- international applications [Windows Forms], character display
- StatusBar control [Windows Forms], lack of Unicode support
- MonthCalendar control [Windows Forms], lack of Unicode support
- international characters
- TabControl control [Windows Forms], lack of Unicode support
- Windows Forms, encoding
- TreeView control [Windows Forms], lack of Unicode support
- ProgressBar control [Windows Forms], Unicode-enabled forms
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: 22e8965d-a712-42b3-8167-3ee346bd70f9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cbac07e92d892913f2d2a342b2fa5b3d5fe2f40c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="encoding-and-windows-forms-globalization"></a><span data-ttu-id="35175-102">Globalizzazione di Windows Form e codifica</span><span class="sxs-lookup"><span data-stu-id="35175-102">Encoding and Windows Forms Globalization</span></span>
<span data-ttu-id="35175-103">Le applicazioni Windows Forms sono completamente compatibili con Unicode, vale a dire che ogni carattere è rappresentato da un numero univoco, indipendentemente dalla piattaforma, dal programma o dal linguaggio in uso.</span><span class="sxs-lookup"><span data-stu-id="35175-103">Windows Forms applications are entirely Unicode-enabled, meaning that each character is represented by a unique number, no matter what the platform, program, or language.</span></span> <span data-ttu-id="35175-104">Per ulteriori informazioni su Unicode, vedere il [sito Web di Unicode consortium](http://www.unicode.org).</span><span class="sxs-lookup"><span data-stu-id="35175-104">For more information about Unicode, see the [Unicode consortium Web site](http://www.unicode.org).</span></span>  
  
## <a name="benefits-of-unicode"></a><span data-ttu-id="35175-105">Vantaggi di Unicode</span><span class="sxs-lookup"><span data-stu-id="35175-105">Benefits of Unicode</span></span>  
 <span data-ttu-id="35175-106">I vantaggi dei form abilitati per Unicode includono la possibilità di lavorare con gli script solo Unicode, ad esempio l'Hindi.</span><span class="sxs-lookup"><span data-stu-id="35175-106">The benefits of Unicode-enabled forms include the ability to work with scripts that are Unicode-only, such as Hindi.</span></span> <span data-ttu-id="35175-107">È anche possibile usare più lingue in un unico form.</span><span class="sxs-lookup"><span data-stu-id="35175-107">In addition, you can use multiple languages on a single form.</span></span> <span data-ttu-id="35175-108">In Unicode tutti i caratteri sono lunghi due byte, quindi non occorrono operazioni complesse per rappresentare i caratteri DBCS.</span><span class="sxs-lookup"><span data-stu-id="35175-108">In Unicode, all characters are two bytes long, so no special effort is needed to represent double-byte characters.</span></span> <span data-ttu-id="35175-109">È anche possibile scrivere un singolo set di codice che funzionerà su tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="35175-109">You can also write a single set of code that will work on all platforms.</span></span> <span data-ttu-id="35175-110">Si tratta di una modifica rispetto alle versioni precedenti di [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], in cui era necessario scrivere codice diverso per piattaforme diverse, ad esempio Windows NT e [!INCLUDE[win98](../../../../includes/win98-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35175-110">This is a change from previous versions of [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], in which you had to write different code for different platforms, such as Windows NT and [!INCLUDE[win98](../../../../includes/win98-md.md)].</span></span>  
  
 <span data-ttu-id="35175-111">Tuttavia, alcuni controlli non supportano Unicode in [!INCLUDE[win98](../../../../includes/win98-md.md)] e Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="35175-111">However, certain controls do not support Unicode in [!INCLUDE[win98](../../../../includes/win98-md.md)] and Windows Millennium Edition.</span></span> <span data-ttu-id="35175-112">Questi controlli, tutti eredi del controllo comune, elaborano i dati con le tabelle codici di Windows, ad esempio [!INCLUDE[vcpransi](../../../../includes/vcpransi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35175-112">These controls, all of which inherit from the common control, will process data with the Windows code pages, as [!INCLUDE[vcpransi](../../../../includes/vcpransi-md.md)].</span></span> <span data-ttu-id="35175-113">Questi controlli sono: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar> e <xref:System.Windows.Forms.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="35175-113">These controls are: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar>, and <xref:System.Windows.Forms.StatusBar>.</span></span> <span data-ttu-id="35175-114">Di conseguenza, non è possibile visualizzare i dati Unicode in questi controlli sulle piattaforme elencate.</span><span class="sxs-lookup"><span data-stu-id="35175-114">As a result, you cannot display Unicode data in these controls on the listed platforms.</span></span> <span data-ttu-id="35175-115">Ad esempio, non è possibile visualizzare caratteri giapponesi in un sistema operativo [!INCLUDE[win98](../../../../includes/win98-md.md)] in inglese.</span><span class="sxs-lookup"><span data-stu-id="35175-115">For example, you cannot display Japanese characters on an English [!INCLUDE[win98](../../../../includes/win98-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="35175-116">Per alternative con supporto Unicode a <xref:System.Windows.Forms.ToolBar> e <xref:System.Windows.Forms.StatusBar>, usare i controlli <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.StatusStrip> che sostituiscono i controlli precedenti.</span><span class="sxs-lookup"><span data-stu-id="35175-116">For Unicode-aware alternatives to the <xref:System.Windows.Forms.ToolBar> and <xref:System.Windows.Forms.StatusBar> controls, use the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip> controls, which replace these older controls.</span></span> <span data-ttu-id="35175-117">Per mantenere un aspetto omogeneo tra gli elementi visivi nell'applicazione, usare il controllo <xref:System.Windows.Forms.MenuStrip> al posto di <xref:System.Windows.Forms.MainMenu> per il rendering dei menu.</span><span class="sxs-lookup"><span data-stu-id="35175-117">To maintain a similar look and feel between visual elements in your application, use the <xref:System.Windows.Forms.MenuStrip> control for rendering menus instead of <xref:System.Windows.Forms.MainMenu>.</span></span> <span data-ttu-id="35175-118">Come <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.StatusStrip>, anche <xref:System.Windows.Forms.MenuStrip> può elaborare e visualizzare i caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="35175-118">Like <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip>, <xref:System.Windows.Forms.MenuStrip> can also process and display Unicode characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35175-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35175-119">See Also</span></span>  
 [<span data-ttu-id="35175-120">Globalizzazione di Windows Form</span><span class="sxs-lookup"><span data-stu-id="35175-120">Globalizing Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)
