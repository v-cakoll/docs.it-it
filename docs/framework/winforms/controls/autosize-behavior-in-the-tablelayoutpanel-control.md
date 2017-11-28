---
title: Comportamento di AutoSize nel controllo TableLayoutPanel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3d4813b7bd37c0c5bd9b04b37cb825067b35ce3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a><span data-ttu-id="d8473-102">Comportamento di AutoSize nel controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d8473-102">AutoSize Behavior in the TableLayoutPanel Control</span></span>
## <a name="distinct-autosize-behaviors"></a><span data-ttu-id="d8473-103">Diversi comportamenti di AutoSize</span><span class="sxs-lookup"><span data-stu-id="d8473-103">Distinct AutoSize Behaviors</span></span>  
 <span data-ttu-id="d8473-104">Il <xref:System.Windows.Forms.TableLayoutPanel> controllo supporta il ridimensionamento automatico nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8473-104">The <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior in the following ways:</span></span>  
  
-   <span data-ttu-id="d8473-105">Tramite il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="d8473-105">Through the <xref:System.Windows.Forms.Control.AutoSize%2A> property;</span></span>  
  
-   <span data-ttu-id="d8473-106">Tramite il <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> proprietà il <xref:System.Windows.Forms.TableLayoutPanel> stili per riga e colonna del controllo.</span><span class="sxs-lookup"><span data-stu-id="d8473-106">Through the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property on the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a><span data-ttu-id="d8473-107">La proprietà AutoSize con stili di colonna e riga</span><span class="sxs-lookup"><span data-stu-id="d8473-107">The AutoSize Property with Row and Column Styles</span></span>  
 <span data-ttu-id="d8473-108">Nella tabella seguente viene descritta l'interazione tra il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà e <xref:System.Windows.Forms.TableLayoutPanel> stili per riga e colonna del controllo.</span><span class="sxs-lookup"><span data-stu-id="d8473-108">The following table describes the interaction between the <xref:System.Windows.Forms.Control.AutoSize%2A> property and the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
|<span data-ttu-id="d8473-109">Impostazione di AutoSize</span><span class="sxs-lookup"><span data-stu-id="d8473-109">AutoSize setting</span></span>|<span data-ttu-id="d8473-110">Interazione di stile</span><span class="sxs-lookup"><span data-stu-id="d8473-110">Style interaction</span></span>|  
|----------------------|-----------------------|  
|`false`|<span data-ttu-id="d8473-111">Il <xref:System.Windows.Forms.TableLayoutPanel> controllo procede da sinistra a destra e consente di allocare spazio per la colonna o riga o nell'ordine seguente.</span><span class="sxs-lookup"><span data-stu-id="d8473-111">The <xref:System.Windows.Forms.TableLayoutPanel> control proceeds from left to right, and allocates space for the column or row or in the following order.</span></span><br /><br /> <span data-ttu-id="d8473-112">1.  Se il <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> è impostata su <xref:System.Windows.Forms.SizeType.Absolute>, il numero di pixel specificato da <xref:System.Windows.Forms.ColumnStyle.Width%2A> o <xref:System.Windows.Forms.RowStyle.Height%2A> viene allocato.</span><span class="sxs-lookup"><span data-stu-id="d8473-112">1.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.Absolute>, the number of pixels specified by <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> is allocated.</span></span><br /><span data-ttu-id="d8473-113">2.  Se il <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> è impostata su <xref:System.Windows.Forms.SizeType.AutoSize>, il numero di pixel come risultato del controllo figlio <xref:System.Windows.Forms.Control.GetPreferredSize%2A> (metodo) viene allocato.</span><span class="sxs-lookup"><span data-stu-id="d8473-113">2.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.AutoSize>, the number of pixels returned by the child control’s <xref:System.Windows.Forms.Control.GetPreferredSize%2A> method is allocated.</span></span><br /><span data-ttu-id="d8473-114">3.  Spazio per tutte <xref:System.Windows.Forms.SizeType.Absolute> e <xref:System.Windows.Forms.SizeType.AutoSize> colonne o righe viene allocato, le eventuali colonne o righe con <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> impostato su <xref:System.Windows.Forms.SizeType.Percent> vengono utilizzati per allocare in proporzione lo spazio libero rimanente</span><span class="sxs-lookup"><span data-stu-id="d8473-114">3.  After space for all <xref:System.Windows.Forms.SizeType.Absolute> and <xref:System.Windows.Forms.SizeType.AutoSize> columns or rows is allocated, any columns or rows with <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> set to <xref:System.Windows.Forms.SizeType.Percent> are used to proportionally allocate the remaining free space</span></span>|  
|`true`|<span data-ttu-id="d8473-115">Simile all'interazione precedente, con l'eccezione che <xref:System.Windows.Forms.SizeType.Percent> colonne o righe vengono ridimensionate automaticamente di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="d8473-115">Similar to the previous interaction, with the exception that <xref:System.Windows.Forms.SizeType.Percent> columns or rows acquire an automatic sizing aspect.</span></span><br /><br /> <span data-ttu-id="d8473-116">Il <xref:System.Windows.Forms.TableLayoutPanel> controllo espande la colonna o riga per creare lo spazio libero, in modo che nessuna colonna o riga con <xref:System.Windows.Forms.SizeType.Percent> troncare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="d8473-116">The <xref:System.Windows.Forms.TableLayoutPanel> control expands the column or row to create adequate free space, so that no column or row with <xref:System.Windows.Forms.SizeType.Percent> styling clips its contents.</span></span> <span data-ttu-id="d8473-117">Il <xref:System.Windows.Forms.TableLayoutPanel> controllo alloca in modo proporzionale in base al nuovo spazio di <xref:System.Windows.Forms.ColumnStyle.Width%2A> o <xref:System.Windows.Forms.RowStyle.Height%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="d8473-117">The <xref:System.Windows.Forms.TableLayoutPanel> control allocates the new space proportionally according to the <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8473-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8473-118">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="d8473-119">Panoramica del controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d8473-119">TableLayoutPanel Control Overview</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)
