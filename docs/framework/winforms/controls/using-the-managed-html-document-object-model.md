---
title: Utilizzare il Document Object Model HTML gestito
ms.date: 03/30/2017
helpviewer_keywords:
- managed HTML DOM
ms.assetid: a017dd5c-cd7b-47e4-952c-f4f54cb48409
ms.openlocfilehash: c18c6df29f79e9bde8474fa38e45dea03d4e0020
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009164"
---
# <a name="using-the-managed-html-document-object-model"></a><span data-ttu-id="1b7f6-102">Utilizzare il Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="1b7f6-102">Using the Managed HTML Document Object Model</span></span>
<span data-ttu-id="1b7f6-103">Il modello a oggetti documento (DOM) HTML gestito fornisce un wrapper di base di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per le classi HTML esposte da Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="1b7f6-103">The managed HTML document object model (DOM) provides a wrapper based on the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] for the HTML classes exposed by Internet Explorer.</span></span> <span data-ttu-id="1b7f6-104">Usare queste classi per modificare pagine HTML ospitate nel <xref:System.Windows.Forms.WebBrowser> (controllo), o per creare nuove pagine dall'inizio.</span><span class="sxs-lookup"><span data-stu-id="1b7f6-104">Use these classes to manipulate HTML pages hosted in the <xref:System.Windows.Forms.WebBrowser> control, or to build new pages from the beginning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b7f6-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="1b7f6-105">In This Section</span></span>  
 [<span data-ttu-id="1b7f6-106">Procedura: Accedere al modello a oggetti documenti HTML gestito</span><span class="sxs-lookup"><span data-stu-id="1b7f6-106">How to: Access the Managed HTML Document Object Model</span></span>](how-to-access-the-managed-html-document-object-model.md)  
 <span data-ttu-id="1b7f6-107">Descrive come ottenere un'istanza valida del <xref:System.Windows.Forms.HtmlDocument> utilizzando un'applicazione Windows Form o un <xref:System.Windows.Forms.UserControl> ospitata in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="1b7f6-107">Describes how to obtain a valid instance of <xref:System.Windows.Forms.HtmlDocument> from either a Windows Forms application or a <xref:System.Windows.Forms.UserControl> hosted in Internet Explorer.</span></span>  
  
 [<span data-ttu-id="1b7f6-108">Procedura: Accedere all'origine HTML nel modello a oggetti documento HTML gestito</span><span class="sxs-lookup"><span data-stu-id="1b7f6-108">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>](how-to-access-the-html-source-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="1b7f6-109">Viene descritto come ottenere l'origine HTML originale, non modificato e come ottenere l'origine "live" che riflette lo stato corrente del DOM.</span><span class="sxs-lookup"><span data-stu-id="1b7f6-109">Describes how to obtain the original, unmodified HTML source, and how to obtain the "live" source that reflects the current state of the DOM.</span></span>  
  
 [<span data-ttu-id="1b7f6-110">Procedura: Modificare gli stili di un elemento nel modello a oggetti documento HTML gestito</span><span class="sxs-lookup"><span data-stu-id="1b7f6-110">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>](how-to-change-styles-on-an-element-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="1b7f6-111">Viene descritto come modificare gli stili, vengono usati per controllare l'aspetto visivo degli elementi.</span><span class="sxs-lookup"><span data-stu-id="1b7f6-111">Describes how to manipulate styles, which are used to control the visual display of elements.</span></span>  
  
 [<span data-ttu-id="1b7f6-112">Accesso a frame nel Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="1b7f6-112">Accessing Frames in the Managed HTML Document Object Model</span></span>](accessing-frames-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="1b7f6-113">Descrive che cosa sono i frame e pagine con frame e su come accedere al DOM di un frame.</span><span class="sxs-lookup"><span data-stu-id="1b7f6-113">Describes what frames and framesets are, and how to access the DOM of a frame.</span></span>  
  
 [<span data-ttu-id="1b7f6-114">Accesso ai membri non esposti del Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="1b7f6-114">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>](accessing-unexposed-members-on-the-managed-html-document-object-model.md)  
 <span data-ttu-id="1b7f6-115">Viene descritto come accedere ai membri del DOM sottostante che non possiedono un equivalente gestito.</span><span class="sxs-lookup"><span data-stu-id="1b7f6-115">Describes how to access members of the underlying DOM that do not have a managed equivalent.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1b7f6-116">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="1b7f6-116">Reference</span></span>  
 <xref:System.Windows.Forms.HtmlDocument>  
  
 <xref:System.Windows.Forms.HtmlElement>  
  
 <xref:System.Windows.Forms.HtmlWindow>  
  
## <a name="related-sections"></a><span data-ttu-id="1b7f6-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="1b7f6-117">Related Sections</span></span>  
 [<span data-ttu-id="1b7f6-118">Controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="1b7f6-118">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)  
