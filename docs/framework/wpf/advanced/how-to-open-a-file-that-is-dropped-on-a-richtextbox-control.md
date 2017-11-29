---
title: 'Procedura: aprire un file rilasciato in un controllo RichTextBox'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f65ecaf9c6ef34176967e1ebf9134ceee195036b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a><span data-ttu-id="044f1-102">Procedura: aprire un file rilasciato in un controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="044f1-102">How to: Open a File That is Dropped on a RichTextBox Control</span></span>
<span data-ttu-id="044f1-103">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, e <xref:System.Windows.Documents.FlowDocument> tutti i controlli sono incorporate funzionalità di trascinamento e rilascio.</span><span class="sxs-lookup"><span data-stu-id="044f1-103">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], the <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> controls all have built-in drag-and-drop functionality.</span></span> <span data-ttu-id="044f1-104">La funzionalità incorporata consente di trascinamento e rilascio del testo all'interno e tra i controlli.</span><span class="sxs-lookup"><span data-stu-id="044f1-104">The built-in functionality enables drag-and-drop of text within and between the controls.</span></span> <span data-ttu-id="044f1-105">Tuttavia, non consente l'apertura di un file eliminando il file nel controllo.</span><span class="sxs-lookup"><span data-stu-id="044f1-105">However, it does not enable opening a file by dropping the file on the control.</span></span> <span data-ttu-id="044f1-106">Questi controlli inoltre contrassegnano gli eventi di trascinamento e rilascio come gestito.</span><span class="sxs-lookup"><span data-stu-id="044f1-106">These controls also mark the drag-and-drop events as handled.</span></span> <span data-ttu-id="044f1-107">Di conseguenza, per impostazione predefinita, è possibile aggiungere i propri gestori eventi per fornire la funzionalità di apertura file rilasciati.</span><span class="sxs-lookup"><span data-stu-id="044f1-107">As a result, by default, you cannot add your own event handlers to provide functionality to open dropped files.</span></span>  
  
 <span data-ttu-id="044f1-108">Per aggiungere ulteriori operazioni di gestione per gli eventi di trascinamento e rilascio in questi controlli, utilizzare il <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> metodo per aggiungere i gestori eventi per gli eventi di trascinamento e rilascio.</span><span class="sxs-lookup"><span data-stu-id="044f1-108">To add additional handling for drag-and-drop events in these controls, use the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method to add your event handlers for the drag-and-drop events.</span></span> <span data-ttu-id="044f1-109">Impostare il `handledEventsToo` parametro `true` per il gestore specificato venga richiamato per un evento indirizzato è già stato contrassegnato come gestito da un altro elemento lungo la route dell'evento.</span><span class="sxs-lookup"><span data-stu-id="044f1-109">Set the `handledEventsToo` parameter to `true` to have the specified handler be invoked for a routed event that has already been marked as handled by another element along the event route.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="044f1-110">È possibile sostituire la funzionalità di trascinamento e rilascio predefinita di <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, e <xref:System.Windows.Documents.FlowDocument> gestendo le versioni di anteprima degli eventi di trascinamento e rilascio e contrassegnare gli eventi di anteprima come gestito.</span><span class="sxs-lookup"><span data-stu-id="044f1-110">You can replace the built-in drag-and-drop functionality of <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> by handling the preview versions of the drag-and-drop events and marking the preview events as handled.</span></span> <span data-ttu-id="044f1-111">Tuttavia, questo disabiliterà la funzionalità di trascinamento e rilascio predefinita e non è consigliato.</span><span class="sxs-lookup"><span data-stu-id="044f1-111">However, this will disable the built-in drag-and-drop functionality, and is not recommended.</span></span>  
  
## <a name="example"></a><span data-ttu-id="044f1-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="044f1-112">Example</span></span>  
 <span data-ttu-id="044f1-113">Nell'esempio seguente viene illustrato come aggiungere i gestori per il <xref:System.Windows.DragDrop.DragOver> e <xref:System.Windows.DragDrop.Drop> eventi su un <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="044f1-113">The following example demonstrates how to add handlers for the <xref:System.Windows.DragDrop.DragOver> and <xref:System.Windows.DragDrop.Drop> events on a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="044f1-114">Questo esempio viene utilizzato il <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> (metodo) e imposta il `handledEventsToo` parametro `true` in modo che verranno richiamati anche se i gestori degli eventi il <xref:System.Windows.Controls.RichTextBox> contrassegna questi eventi come gestito.</span><span class="sxs-lookup"><span data-stu-id="044f1-114">This example uses the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method and sets the `handledEventsToo` parameter to `true` so that the events handlers will be invoked even though the <xref:System.Windows.Controls.RichTextBox> marks these events as handled.</span></span> <span data-ttu-id="044f1-115">Il codice nei gestori di eventi consente di aprire un file di testo che viene eliminato il <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="044f1-115">The code in the event handlers adds functionality to open a text file that is dropped on the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="044f1-116">Per testare questo esempio, trascinare un file di testo o un file di formato RTF RTF da Esplora risorse per il <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="044f1-116">To test this example, drag a text file or a rich text format (RTF) file from Windows Explorer to the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="044f1-117">Il file verrà aperto nel <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="044f1-117">The file will be opened in the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="044f1-118">Se si preme il tasto MAIUSC prima di eliminare il file, verrà aperto il file come testo normale.</span><span class="sxs-lookup"><span data-stu-id="044f1-118">If you press the SHIFT key before the dropping the file, the file will be opened as plain text.</span></span>  
  
 [!code-xaml[DragDropSnippets#RtbXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
