---
title: App non gestite
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: 17dc20653d1628dfd460a9891e1b0a21c0ebecbd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746360"
---
# <a name="windows-forms-and-unmanaged-applications"></a><span data-ttu-id="1ef45-102">Windows Form e applicazioni non gestite</span><span class="sxs-lookup"><span data-stu-id="1ef45-102">Windows Forms and Unmanaged Applications</span></span>
<span data-ttu-id="1ef45-103">Le applicazioni e i controlli Windows Form possono interagire con le applicazioni non gestite, con alcune raccomandazioni.</span><span class="sxs-lookup"><span data-stu-id="1ef45-103">Windows Forms applications and controls can interoperate with unmanaged applications, with some caveats.</span></span> <span data-ttu-id="1ef45-104">Nelle sezioni che seguono vengono descritti configurazioni e scenari supportati e non supportati dalle applicazioni e dai controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1ef45-104">The following sections describe the scenarios and configurations that Windows Forms applications and controls support and those that they do not support.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ef45-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1ef45-105">In This Section</span></span>  
 [<span data-ttu-id="1ef45-106">Panoramica su Windows Form e applicazioni non gestite</span><span class="sxs-lookup"><span data-stu-id="1ef45-106">Windows Forms and Unmanaged Applications Overview</span></span>](windows-forms-and-unmanaged-applications-overview.md)  
 <span data-ttu-id="1ef45-107">Fornisce informazioni generali su come usare e implementare i controlli Windows Form che funzionano con le applicazioni non gestite.</span><span class="sxs-lookup"><span data-stu-id="1ef45-107">Offers general information about how to use and implement Windows Forms controls that work with unmanaged applications.</span></span>  
  
 [<span data-ttu-id="1ef45-108">Procedura: Supportare l'interoperabilità COM visualizzando un Windows Form con il metodo ShowDialog</span><span class="sxs-lookup"><span data-stu-id="1ef45-108">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>](com-interop-by-displaying-a-windows-form-shadow.md)  
 <span data-ttu-id="1ef45-109">Fornisce un esempio di codice che illustra come usare il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> per l'esecuzione di un Windows Form in un'applicazione non gestita.</span><span class="sxs-lookup"><span data-stu-id="1ef45-109">Provides a code example that shows how to use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to run a Windows Form in an unmanaged application.</span></span>  
  
 [<span data-ttu-id="1ef45-110">Procedura: supportare l'interoperabilità COM mediante la visualizzazione di ogni Windows Form nel relativo thread</span><span class="sxs-lookup"><span data-stu-id="1ef45-110">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 <span data-ttu-id="1ef45-111">Fornisce un esempio di codice che illustra come eseguire un Windows Form nel relativo thread.</span><span class="sxs-lookup"><span data-stu-id="1ef45-111">Provides a code example that shows how to run a Windows Form on its own thread.</span></span>  
  
 <span data-ttu-id="1ef45-112">Vedere anche [Procedura dettagliata: supporto dell'interoperabilità COM mediante la visualizzazione di ogni Windows Form nel relativo thread](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="1ef45-112">Also see [Walkthrough: Supporting COM Interop by Displaying Each Windows Form on Its Own Thread](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1ef45-113">Riferimento</span><span class="sxs-lookup"><span data-stu-id="1ef45-113">Reference</span></span>  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 <span data-ttu-id="1ef45-114">Usato per creare un thread separato per un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1ef45-114">Used to create a separate thread for a Windows Form.</span></span>  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 <span data-ttu-id="1ef45-115">Avvia un ciclo di messaggi per un thread.</span><span class="sxs-lookup"><span data-stu-id="1ef45-115">Starts a message loop for a thread.</span></span>  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 <span data-ttu-id="1ef45-116">Effettua il marshalling di chiamate da un'applicazione non gestita a un form.</span><span class="sxs-lookup"><span data-stu-id="1ef45-116">Marshals calls from an unmanaged application to a form.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1ef45-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="1ef45-117">Related Sections</span></span>  
 [<span data-ttu-id="1ef45-118">Esposizione di componenti .NET Framework a COM</span><span class="sxs-lookup"><span data-stu-id="1ef45-118">Exposing .NET Framework Components to COM</span></span>](../../interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="1ef45-119">Fornisce informazioni generali sull'uso di tipi .NET Framework nelle applicazioni non gestite.</span><span class="sxs-lookup"><span data-stu-id="1ef45-119">Offers general information about how to use .NET Framework types in unmanaged applications.</span></span>
