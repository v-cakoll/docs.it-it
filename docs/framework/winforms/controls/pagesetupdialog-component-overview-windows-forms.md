---
title: Cenni preliminari sul componente PageSetupDialog (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: 30ac782cae830ac996132046cbbc57392067c0ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228315"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a><span data-ttu-id="70143-102">Cenni preliminari sul componente PageSetupDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="70143-102">PageSetupDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="70143-103">I moduli di Windows <xref:System.Windows.Forms.PageSetupDialog> componente è una finestra di dialogo preconfigurata che consente di impostare i dettagli della pagina per la stampa nelle applicazioni basate su Windows.</span><span class="sxs-lookup"><span data-stu-id="70143-103">The Windows Forms <xref:System.Windows.Forms.PageSetupDialog> component is a pre-configured dialog box used to set page details for printing in Windows-based applications.</span></span> <span data-ttu-id="70143-104">Usarlo all'interno dell'applicazione basata su Windows come una soluzione semplice per gli utenti per impostare preferenze delle pagine anziché configurare una propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="70143-104">Use it within your Windows-based application as a simple solution for users to set page preferences in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="70143-105">È possibile abilitare gli utenti di impostare i bordi e i margini, intestazioni e piè di pagina e l'orientamento verticale o orizzontale.</span><span class="sxs-lookup"><span data-stu-id="70143-105">You can enable users to set border and margin adjustments, headers and footers, and portrait or landscape orientation.</span></span> <span data-ttu-id="70143-106">Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti.</span><span class="sxs-lookup"><span data-stu-id="70143-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="70143-107">I metodi e proprietà chiave</span><span class="sxs-lookup"><span data-stu-id="70143-107">Key Properties and Methods</span></span>  
 <span data-ttu-id="70143-108">Usare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="70143-108">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="70143-109">Il componente include proprietà che è possibile impostare relative a una singola pagina (<xref:System.Drawing.Printing.PrintDocument> classe) o dei documenti (<xref:System.Drawing.Printing.PageSettings> classe).</span><span class="sxs-lookup"><span data-stu-id="70143-109">This component has properties you can set that relate to either a single page (<xref:System.Drawing.Printing.PrintDocument> class) or any document (<xref:System.Drawing.Printing.PageSettings> class).</span></span> <span data-ttu-id="70143-110">Inoltre, il <xref:System.Windows.Forms.PageSetupDialog> componente può essere utilizzato per determinare le impostazioni della stampante specifici, che vengono archiviate nel <xref:System.Drawing.Printing.PrinterSettings> classe.</span><span class="sxs-lookup"><span data-stu-id="70143-110">Additionally, the <xref:System.Windows.Forms.PageSetupDialog> component can be used to determine specific printer settings, which are stored in the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span>  
  
 <span data-ttu-id="70143-111">Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.PageSetupDialog> componente è visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="70143-111">When it is added to a form, the <xref:System.Windows.Forms.PageSetupDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70143-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70143-112">See also</span></span>

- <xref:System.Windows.Forms.PageSetupDialog>
- [<span data-ttu-id="70143-113">Componente PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="70143-113">PageSetupDialog Component</span></span>](pagesetupdialog-component-windows-forms.md)
