---
title: Multithreading nei controlli Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cf6790172b7445ad154eead5d17f8efddd78ffee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952671"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="6a7fc-102">Multithreading nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="6a7fc-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="6a7fc-103">In molte applicazioni è possibile rendere più reattive l'interfaccia utente eseguendo operazioni che richiedono molto tempo in un altro thread.</span><span class="sxs-lookup"><span data-stu-id="6a7fc-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="6a7fc-104">Sono disponibili diversi strumenti per il multithreading dei controlli di Windows Forms, tra cui <xref:System.Threading> lo spazio dei <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> nomi, il metodo `BackgroundWorker` e il componente.</span><span class="sxs-lookup"><span data-stu-id="6a7fc-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a7fc-105">Il `BackgroundWorker` componente sostituisce e aggiunge funzionalità allo spazio <xref:System.Threading> dei nomi e <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> al metodo. questi elementi vengono tuttavia conservati sia per la compatibilità con le versioni precedenti che per un uso futuro, se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="6a7fc-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="6a7fc-106">Per ulteriori informazioni, vedere [Cenni preliminari sul componente BackgroundWorker](backgroundworker-component-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6a7fc-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6a7fc-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="6a7fc-107">In This Section</span></span>  
 [<span data-ttu-id="6a7fc-108">Procedura: Eseguire chiamate thread-safe a controlli Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a7fc-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="6a7fc-109">Viene illustrato come eseguire chiamate thread-safe a controlli Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6a7fc-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="6a7fc-110">Procedura: Usare un thread in background per la ricerca di file</span><span class="sxs-lookup"><span data-stu-id="6a7fc-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="6a7fc-111">Viene illustrato come utilizzare lo <xref:System.Threading> spazio dei nomi <xref:System.Windows.Forms.Control.BeginInvoke%2A> e il metodo per cercare i file in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="6a7fc-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6a7fc-112">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="6a7fc-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="6a7fc-113">Documenta un componente che incapsula un thread di lavoro per le operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="6a7fc-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="6a7fc-114">Documenta come caricare un suono in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="6a7fc-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="6a7fc-115">Documenta come caricare un'immagine in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="6a7fc-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6a7fc-116">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="6a7fc-116">Related Sections</span></span>  
 [<span data-ttu-id="6a7fc-117">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="6a7fc-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="6a7fc-118">Viene illustrato come eseguire un'operazione che richiede molto tempo con il <xref:System.ComponentModel.BackgroundWorker> componente.</span><span class="sxs-lookup"><span data-stu-id="6a7fc-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="6a7fc-119">Panoramica sul componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="6a7fc-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="6a7fc-120">Fornisce argomenti che descrivono come utilizzare il <xref:System.ComponentModel.BackgroundWorker> componente per le operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="6a7fc-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
