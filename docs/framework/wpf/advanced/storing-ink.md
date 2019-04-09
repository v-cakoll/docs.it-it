---
title: Memorizzazione dell'input penna
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ISF (Ink Serialized Format)
- storing ink [WPF]
- ink [WPF], storing
- retrieving ink [WPF]
- Ink Serialized Format (ISF)
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
ms.openlocfilehash: 4089aa7942105c14eb628c75edb7f53ffacfaeb0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182338"
---
# <a name="storing-ink"></a><span data-ttu-id="cf888-102">Memorizzazione dell'input penna</span><span class="sxs-lookup"><span data-stu-id="cf888-102">Storing Ink</span></span>
<span data-ttu-id="cf888-103">Il <xref:System.Windows.Ink.StrokeCollection.Save%2A> metodi forniscono supporto per l'archiviazione dell'input penna in formato ISF (Ink Serialized Format).</span><span class="sxs-lookup"><span data-stu-id="cf888-103">The <xref:System.Windows.Ink.StrokeCollection.Save%2A> methods provide support for storing ink as Ink Serialized Format (ISF).</span></span> <span data-ttu-id="cf888-104">I costruttori per la <xref:System.Windows.Ink.StrokeCollection> classi forniscono supporto per la lettura dei dati di input penna.</span><span class="sxs-lookup"><span data-stu-id="cf888-104">Constructors for the <xref:System.Windows.Ink.StrokeCollection> class provide support for reading ink data.</span></span>  
  
## <a name="ink-storage-and-retrieval"></a><span data-ttu-id="cf888-105">Archiviazione dell'input penna e il recupero</span><span class="sxs-lookup"><span data-stu-id="cf888-105">Ink Storage and Retrieval</span></span>  
 <span data-ttu-id="cf888-106">Questa sezione illustra come archiviare e recuperare l'input penna nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] piattaforma.</span><span class="sxs-lookup"><span data-stu-id="cf888-106">This section discusses how to store and retrieve ink in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] platform.</span></span>  
  
 <span data-ttu-id="cf888-107">L'esempio seguente implementa un gestore eventi clic del pulsante che presenta all'utente una finestra di dialogo Salva File e Salva l'input penna da un <xref:System.Windows.Controls.InkCanvas> out in un file.</span><span class="sxs-lookup"><span data-stu-id="cf888-107">The following example implements a button-click event handler that presents the user with a File Save dialog box and saves the ink from an <xref:System.Windows.Controls.InkCanvas> out to a file.</span></span>  
  
 [!code-csharp[DigitalInkTopics#12](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 <span data-ttu-id="cf888-108">L'esempio seguente implementa un gestore eventi clic del pulsante che presenta all'utente una finestra di dialogo Apri File e legge l'input penna dal file in un <xref:System.Windows.Controls.InkCanvas> elemento.</span><span class="sxs-lookup"><span data-stu-id="cf888-108">The following example implements a button-click event handler that presents the user with a File Open dialog box and reads ink from the file into an <xref:System.Windows.Controls.InkCanvas> element.</span></span>  
  
 [!code-csharp[DigitalInkTopics#13](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="cf888-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf888-109">See also</span></span>

- <xref:System.Windows.Controls.InkCanvas>
- [<span data-ttu-id="cf888-110">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="cf888-110">Windows Presentation Foundation</span></span>](../index.md)
