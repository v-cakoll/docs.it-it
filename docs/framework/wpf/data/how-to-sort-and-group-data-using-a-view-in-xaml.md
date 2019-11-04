---
title: 'Procedura: ordinare e raggruppare i dati tramite una visualizzazione di XAML'
ms.date: 03/30/2017
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
ms.openlocfilehash: 9e42dd330535f71438ab7af3dca9d078e9dfd8d3
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460121"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>Procedura: ordinare e raggruppare i dati tramite una visualizzazione di XAML
Questo esempio illustra come creare una vista di una raccolta dati in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Le visualizzazioni consentono le funzionalità di raggruppamento, ordinamento, filtro e la nozione di elemento corrente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, la risorsa statica denominata *Places* viene definita come una raccolta di oggetti *Place* , in cui ogni oggetto *Place* è costituito da un nome di città e dallo stato. Il prefisso *src* viene mappato allo spazio dei nomi in cui è definita *l'origine dati* . Il prefisso *SCM* esegue il mapping a `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` e *dat* viene mappato a `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.  
  
 Nell'esempio seguente viene creata una vista della raccolta di dati ordinata in base al nome della città e raggruppata in base allo stato.  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 La vista può quindi essere un'origine di binding, come nell'esempio seguente:  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 Per i binding ai dati XML definiti in una risorsa <xref:System.Windows.Data.XmlDataProvider>, anteporre il nome XML a un simbolo @.  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.CollectionViewSource>
- [Ottenere la visualizzazione predefinita di una raccolta dati](how-to-get-the-default-view-of-a-data-collection.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
