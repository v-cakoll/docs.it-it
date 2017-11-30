---
title: 'Procedura: ordinare e raggruppare i dati tramite una visualizzazione di XAML'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c219def87e258a2c9fc1bf4f4867287e6156c59a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>Procedura: ordinare e raggruppare i dati tramite una visualizzazione di XAML
In questo esempio viene illustrato come creare una visualizzazione di una raccolta di dati in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Le viste consentono per le funzionalità di raggruppamento, ordinamento, filtro e la nozione di un elemento corrente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, la risorsa statica denominata *inserisce* è definito come una raccolta di *sul posto* oggetti, in cui ogni *sul posto* oggetto è costituito da un nome di città e la stato. Il prefisso *src* viene eseguito il mapping allo spazio dei nomi in cui l'origine dati *posizioni* è definito. Il prefisso *scm* esegue il mapping a `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` e *dat* esegue il mapping a `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.  
  
 L'esempio seguente crea una vista della raccolta di dati ordinata in base al nome della città e raggruppata in base allo stato.  
  
 [!code-xaml[CollectionViewSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 La vista può essere quindi un'origine di associazione, come nell'esempio seguente:  
  
 [!code-xaml[CollectionViewSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 Per le associazioni ai dati XML definiti in un <xref:System.Windows.Data.XmlDataProvider> risorsa, anteporre al nome XML con un simbolo @.  
  
 [!code-xaml[CollectionViewSource#XDPChunk](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Data.CollectionViewSource>  
 [Ottenere la visualizzazione predefinita di una raccolta dati](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)  
 [Cenni preliminari sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
