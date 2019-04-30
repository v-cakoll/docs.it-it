---
title: 'Procedura: Usare una griglia per il layout automatico'
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 590ad7292fea572b20ccaa09ce2886724e004a6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052404"
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a><span data-ttu-id="1969f-102">Procedura: Usare una griglia per il layout automatico</span><span class="sxs-lookup"><span data-stu-id="1969f-102">How to: Use a Grid for Automatic Layout</span></span>
<span data-ttu-id="1969f-103">Questo esempio descrive come usare una griglia nell'approccio basato sul layout automatico per la creazione di un'applicazione localizzabile.</span><span class="sxs-lookup"><span data-stu-id="1969f-103">This example describes how to use a grid in the automatic layout approach to creating a localizable application.</span></span>  
  
 <span data-ttu-id="1969f-104">Localizzazione di un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] può essere un processo molto tempo.</span><span class="sxs-lookup"><span data-stu-id="1969f-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="1969f-105">Spesso sono necessari il ridimensionamento e il riposizionamento degli elementi, oltre alla traduzione del testo.</span><span class="sxs-lookup"><span data-stu-id="1969f-105">Often localizers need to re-size and reposition elements in addition to translating text.</span></span> <span data-ttu-id="1969f-106">In precedenza ogni lingua che un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] richiedeva delle modifiche è stato adattato.</span><span class="sxs-lookup"><span data-stu-id="1969f-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="1969f-107">Ora con le funzionalità di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è possibile progettare elementi che riducono la necessità di modifiche.</span><span class="sxs-lookup"><span data-stu-id="1969f-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="1969f-108">Viene chiamato l'approccio alla scrittura di applicazioni che possono risultare più semplice ridimensionare e riposizionare `auto layout`.</span><span class="sxs-lookup"><span data-stu-id="1969f-108">The approach to writing applications that can be more easily re-sized and repositioned is called `auto layout`.</span></span>  
  
 <span data-ttu-id="1969f-109">Nell'esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] viene illustrato l'utilizzo di una griglia per posizionare alcuni pulsanti e del testo.</span><span class="sxs-lookup"><span data-stu-id="1969f-109">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="1969f-110">Si noti che l'altezza e la larghezza delle celle sono impostate per `Auto`; pertanto la cella che contiene il pulsante con un'immagine viene modificata per adattarsi all'immagine.</span><span class="sxs-lookup"><span data-stu-id="1969f-110">Notice that the height and width of the cells are set to `Auto`; therefore the cell that contains the button with an image adjusts to fit the image.</span></span> <span data-ttu-id="1969f-111">Poiché il <xref:System.Windows.Controls.Grid> elemento regolato in base al relativo contenuto può essere utile quando si acquisisce l'approccio di layout automatico per la progettazione di applicazioni che possono essere localizzate.</span><span class="sxs-lookup"><span data-stu-id="1969f-111">Because the <xref:System.Windows.Controls.Grid> element can adjust to its content it can be useful when taking the automatic layout approach to designing applications that can be localized.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1969f-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="1969f-112">Example</span></span>  
 <span data-ttu-id="1969f-113">Nell'esempio riportato di seguito viene illustrato come usare una griglia.</span><span class="sxs-lookup"><span data-stu-id="1969f-113">The following example shows how to use a grid.</span></span>  
  
 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="1969f-114">La figura seguente mostra l'output dell'esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="1969f-114">The following graphic shows the output of the code sample.</span></span>  
  
 <span data-ttu-id="1969f-115">![Esempio di Grid](./media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="1969f-115">![Grid example](./media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="1969f-116">Grid</span><span class="sxs-lookup"><span data-stu-id="1969f-116">Grid</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1969f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1969f-117">See also</span></span>

- [<span data-ttu-id="1969f-118">Cenni preliminari sull'utilizzo del layout automatico</span><span class="sxs-lookup"><span data-stu-id="1969f-118">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="1969f-119">Utilizzare un layout automatico per creare un pulsante</span><span class="sxs-lookup"><span data-stu-id="1969f-119">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
