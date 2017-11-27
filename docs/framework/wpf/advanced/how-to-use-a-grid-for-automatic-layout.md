---
title: 'Procedura: Usare una griglia per il layout automatico'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d18563c44381a276d15996dff3f9552c46833b4a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a>Procedura: Usare una griglia per il layout automatico
Questo esempio descrive come usare una griglia nell'approccio basato sul layout automatico per la creazione di un'applicazione localizzabile.  
  
 Localizzazione di un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] può richiedere molto tempo. Spesso sono necessari il ridimensionamento e il riposizionamento degli elementi, oltre alla traduzione del testo. In passato ogni lingua che un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] è stato adattato per la regolazione obbligatoria. Ora con le funzionalità di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è possibile progettare gli elementi che riducono l'esigenza di modifiche. Viene chiamato l'approccio alla scrittura di applicazioni che possono essere più facilmente ridimensionare e riposizionare `auto layout`.  
  
 Nell'esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] viene illustrato l'utilizzo di una griglia per posizionare alcuni pulsanti e testo. Si noti che l'altezza e la larghezza delle celle sono impostate per `Auto`; pertanto la cella che contiene il pulsante con un'immagine adattato l'immagine. Poiché il <xref:System.Windows.Controls.Grid> elemento regolato in base al relativo contenuto può essere utile quando si acquisisce l'approccio di layout automatico per la progettazione di applicazioni che possono essere localizzate.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene illustrato come usare una griglia.  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 La figura seguente mostra l'output dell'esempio di codice.  
  
 ![Esempio di Grid](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")  
Grid  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'utilizzo del layout automatico](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [Utilizzare un layout automatico per creare un pulsante](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)
