---
title: Multithreading nei controlli Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c4651ca9707dcf0fac2edea0f004275cfcf18cf2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="2f307-102">Multithreading nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="2f307-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="2f307-103">In molte applicazioni, è possibile rendere più reattiva l'interfaccia utente (UI) mediante l'esecuzione di operazioni lunghe ed elaborate in un altro thread.</span><span class="sxs-lookup"><span data-stu-id="2f307-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="2f307-104">Una serie di strumenti è disponibile per multithreading dei controlli Windows Form, inclusi il <xref:System.Threading> dello spazio dei nomi, il <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> (metodo) e `BackgroundWorker` componente.</span><span class="sxs-lookup"><span data-stu-id="2f307-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f307-105">Il `BackgroundWorker` componente sostituisce e aggiunge la funzionalità per il <xref:System.Threading> dello spazio dei nomi e <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> metodo; tuttavia, questi vengono mantenuti per compatibilità con le versioni precedenti e per utilizzo futuro, se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="2f307-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="2f307-106">Per ulteriori informazioni, vedere [Cenni preliminari sul componente BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2f307-106">For more information, see [BackgroundWorker Component Overview](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f307-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2f307-107">In This Section</span></span>  
 [<span data-ttu-id="2f307-108">Procedura: Effettuare chiamate thread-safe a controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2f307-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="2f307-109">Viene illustrato come effettuare chiamate thread-safe a controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="2f307-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="2f307-110">Procedura: Usare un thread in background per la ricerca di file</span><span class="sxs-lookup"><span data-stu-id="2f307-110">How to: Use a Background Thread to Search for Files</span></span>](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="2f307-111">Viene illustrato come utilizzare il <xref:System.Threading> dello spazio dei nomi e <xref:System.Windows.Forms.Control.BeginInvoke%2A> metodo per cercare i file in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="2f307-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2f307-112">Riferimento</span><span class="sxs-lookup"><span data-stu-id="2f307-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="2f307-113">Documenti di un componente che incapsula un thread di lavoro per le operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="2f307-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="2f307-114">Viene illustrato come caricare in modo asincrono un suono.</span><span class="sxs-lookup"><span data-stu-id="2f307-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="2f307-115">Viene illustrato come caricare un'immagine in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="2f307-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2f307-116">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="2f307-116">Related Sections</span></span>  
 [<span data-ttu-id="2f307-117">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="2f307-117">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="2f307-118">Viene illustrato come eseguire un'operazione richiede molto tempo con la <xref:System.ComponentModel.BackgroundWorker> componente.</span><span class="sxs-lookup"><span data-stu-id="2f307-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="2f307-119">Panoramica sul componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="2f307-119">BackgroundWorker Component Overview</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 <span data-ttu-id="2f307-120">Fornisce argomenti che descrivono come utilizzare il <xref:System.ComponentModel.BackgroundWorker> componente per le operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="2f307-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
