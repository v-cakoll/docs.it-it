---
title: Multithreading nei controlli Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cc7f358a62c8057abb77e1f5a28544bb6c858d98
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703322"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="84dcd-102">Multithreading nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="84dcd-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="84dcd-103">In molte applicazioni, è possibile rendere più reattiva l'interfaccia utente (UI) eseguendo le operazioni che richiedono molto tempo in un altro thread.</span><span class="sxs-lookup"><span data-stu-id="84dcd-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="84dcd-104">Una serie di strumenti è disponibile per il multithreading dei controlli Windows Form, tra cui il <xref:System.Threading> dello spazio dei nomi, il <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> metodo e il `BackgroundWorker` componente.</span><span class="sxs-lookup"><span data-stu-id="84dcd-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84dcd-105">Il `BackgroundWorker` componente sostituisce e aggiunge funzionalità per il <xref:System.Threading> dello spazio dei nomi e il <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> metodo; tuttavia, questi vengono mantenuti per compatibilità con le versioni precedenti e per un uso futuro, se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="84dcd-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="84dcd-106">Per altre informazioni, vedere [Cenni preliminari sul componente BackgroundWorker](backgroundworker-component-overview.md).</span><span class="sxs-lookup"><span data-stu-id="84dcd-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84dcd-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="84dcd-107">In This Section</span></span>  
 [<span data-ttu-id="84dcd-108">Procedura: Effettuare chiamate Thread-Safe a controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="84dcd-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="84dcd-109">Viene illustrato come effettuare chiamate thread-safe a controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="84dcd-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="84dcd-110">Procedura: Usare un Thread in Background per la ricerca file</span><span class="sxs-lookup"><span data-stu-id="84dcd-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="84dcd-111">Viene illustrato come utilizzare il <xref:System.Threading> dello spazio dei nomi e il <xref:System.Windows.Forms.Control.BeginInvoke%2A> metodo per cercare i file in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="84dcd-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="84dcd-112">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="84dcd-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="84dcd-113">Documenta un componente che incapsula un thread di lavoro per le operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="84dcd-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="84dcd-114">Viene illustrato come caricare in modo asincrono un suono.</span><span class="sxs-lookup"><span data-stu-id="84dcd-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="84dcd-115">Viene illustrato come caricare un'immagine in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="84dcd-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="84dcd-116">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="84dcd-116">Related Sections</span></span>  
 [<span data-ttu-id="84dcd-117">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="84dcd-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="84dcd-118">Viene illustrato come eseguire un'operazione richiede molto tempo con la <xref:System.ComponentModel.BackgroundWorker> componente.</span><span class="sxs-lookup"><span data-stu-id="84dcd-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="84dcd-119">Panoramica sul componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="84dcd-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="84dcd-120">Fornisce argomenti che descrivono come usare il <xref:System.ComponentModel.BackgroundWorker> componente per le operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="84dcd-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
