---
title: Cenni preliminari sul componente PrintDialog (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0b90d94165de6985b43d47809ae57bfcae204f0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="857dc-102">Cenni preliminari sul componente PrintDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="857dc-102">PrintDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="857dc-103">Windows Form [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) componente è una finestra di dialogo preconfigurata che consentono di selezionare una stampante, scegliere le pagine da stampare e indicare altre impostazioni relative alla stampa nelle applicazioni basate su Windows.</span><span class="sxs-lookup"><span data-stu-id="857dc-103">The Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="857dc-104">Questo componente può essere usato come semplice soluzione per la selezione della stampante e delle impostazioni relative alla stampa anziché configurare una propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="857dc-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="857dc-105">È possibile consentire agli utenti di stampare diverse parti dei documenti: stampare tutte, stampa di un intervallo di pagine selezionato o stampare una selezione.</span><span class="sxs-lookup"><span data-stu-id="857dc-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="857dc-106">Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti.</span><span class="sxs-lookup"><span data-stu-id="857dc-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="857dc-107">Il <xref:System.Windows.Forms.PrintDialog> componente eredita il <xref:System.Windows.Forms.CommonDialog> classe.</span><span class="sxs-lookup"><span data-stu-id="857dc-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-component"></a><span data-ttu-id="857dc-108">Utilizzo del componente</span><span class="sxs-lookup"><span data-stu-id="857dc-108">Working with the Component</span></span>  
 <span data-ttu-id="857dc-109">Utilizzare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="857dc-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="857dc-110">Il componente include proprietà relative a un singolo processo di stampa (<xref:System.Drawing.Printing.PrintDocument> classe) o le impostazioni di una singola stampante (<xref:System.Drawing.Printing.PrinterSettings> classe).</span><span class="sxs-lookup"><span data-stu-id="857dc-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="857dc-111">Uno di questi elementi, a sua volta, può essere condiviso da più stampanti.</span><span class="sxs-lookup"><span data-stu-id="857dc-111">Either of these, in turn, may be shared by multiple printers.</span></span>  
  
 <span data-ttu-id="857dc-112">Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.PrintDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="857dc-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="857dc-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="857dc-113">See Also</span></span>  
 <xref:System.Windows.Forms.PrintDialog>  
 [<span data-ttu-id="857dc-114">Componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="857dc-114">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)
