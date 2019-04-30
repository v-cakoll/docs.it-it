---
title: 'Procedura: Ordinare e raggruppare dati tramite una visualizzazione in XAML'
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
ms.openlocfilehash: ca4439b574264ebebfda745f0765f750099bc95f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020738"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>Procedura: Ordinare e raggruppare dati tramite una visualizzazione in XAML
Questo esempio illustra come creare una visualizzazione di una raccolta di dati in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Le viste consentono per le funzionalità di raggruppamento, ordinamento, filtro e la nozione di elemento corrente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, la risorsa statica denominata *inserisce* viene definito come una raccolta di *luogo* oggetti, in cui ogni *luogo* oggetto è costituito da un nome di città e il stato. Il prefisso *src* viene eseguito il mapping allo spazio dei nomi in cui l'origine dati *posizioni* è definito. Il prefisso *scm* esegue il mapping ai `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` e *dat* esegue il mapping a `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.  
  
 L'esempio seguente crea una visualizzazione della raccolta di dati ordinati in base al nome della città e raggruppata per stato.  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 La vista può essere quindi un'origine di associazione, come nell'esempio seguente:  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 Per le associazioni ai dati XML definiti in un <xref:System.Windows.Data.XmlDataProvider> risorsa, far precedere il nome XML con un simbolo @.  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.CollectionViewSource>
- [Ottenere la visualizzazione predefinita di una raccolta dati](how-to-get-the-default-view-of-a-data-collection.md)
- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
