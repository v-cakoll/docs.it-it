---
title: 'Procedura: Utilizzare una griglia per il layout automatico'
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 0eda70a7d8cc5abb70b5043cbaa1d4fc418bb1f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611423"
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a>Procedura: Utilizzare una griglia per il layout automatico
Questo esempio descrive come usare una griglia nell'approccio basato sul layout automatico per la creazione di un'applicazione localizzabile.  
  
 Localizzazione di un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] può essere un processo molto tempo. Spesso sono necessari il ridimensionamento e il riposizionamento degli elementi, oltre alla traduzione del testo. In precedenza ogni lingua che un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] richiedeva delle modifiche è stato adattato. Ora con le funzionalità di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è possibile progettare elementi che riducono la necessità di modifiche. Viene chiamato l'approccio alla scrittura di applicazioni che possono risultare più semplice ridimensionare e riposizionare `auto layout`.  
  
 Nell'esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] viene illustrato l'utilizzo di una griglia per posizionare alcuni pulsanti e del testo. Si noti che l'altezza e la larghezza delle celle sono impostate per `Auto`; pertanto la cella che contiene il pulsante con un'immagine viene modificata per adattarsi all'immagine. Poiché il <xref:System.Windows.Controls.Grid> elemento regolato in base al relativo contenuto può essere utile quando si acquisisce l'approccio di layout automatico per la progettazione di applicazioni che possono essere localizzate.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene illustrato come usare una griglia.  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 La figura seguente mostra l'output dell'esempio di codice.  
  
 ![Esempio di Grid](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")  
Grid  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sull'utilizzo del layout automatico](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)
- [Utilizzare un layout automatico per creare un pulsante](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)
