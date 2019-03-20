---
title: 'Procedura: Utilizzare il layout automatico per creare un pulsante'
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 185bf71d4105d10a2bb85e6a0abd9da63c7d26f0
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185454"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a>Procedura: Utilizzare il layout automatico per creare un pulsante
Questo esempio descrive come usare un approccio basato sul layout automatico per la creazione di un pulsante in un'applicazione localizzabile.  
  
 Localizzazione di un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] può essere un processo molto tempo. Spesso sono necessari il ridimensionamento e il riposizionamento degli elementi, oltre alla traduzione del testo. In precedenza ogni lingua che un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] richiedeva delle modifiche è stato adattato. Ora con le funzionalità di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è possibile progettare elementi che riducono la necessità di modifiche. L'approccio alla scrittura di applicazioni che è possibile ridimensionare e riposizionare con maggiore semplicità viene definito `automatic layout`.  
  
## <a name="example"></a>Esempio  

I seguenti due [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] esempi di creano applicazioni che creano un pulsante, uno con testo in lingua inglese e uno con testo in spagnolo. Il codice è lo stesso ad eccezione del testo. Il pulsante si regola per adattarsi al testo.

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 La figura seguente mostra l'output degli esempi di codice.  
  
 ![Lo stesso pulsante con testo in lingue diverse](./media/globalizationbutton.png "GlobalizationButton")  
Pulsante a ridimensionamento automatico  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'utilizzo del layout automatico](use-automatic-layout-overview.md)
- [Usare una griglia per il layout automatico](how-to-use-a-grid-for-automatic-layout.md)
