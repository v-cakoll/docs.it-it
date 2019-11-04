---
title: Caricamento XAML e proprietà di dipendenza
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom dependency properties [WPF]
- dependency properties [WPF], XAML loading and
- loading XML data [WPF]
ms.assetid: 6eea9f4e-45ce-413b-a266-f08238737bf2
ms.openlocfilehash: 57c25297f995acd1ef307466258b5f4e03cc3098
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459538"
---
# <a name="xaml-loading-and-dependency-properties"></a>Caricamento XAML e proprietà di dipendenza
L'implementazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] corrente del relativo processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dipende implicitamente dalle proprietà di dipendenza. Il processore [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usa metodi del sistema di proprietà per le proprietà di dipendenza al momento del caricamento del codice [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] binario e dell'elaborazione di attributi che sono proprietà di dipendenza. Ciò consente di ignorare in modo efficace i wrapper della proprietà. Quando si implementano proprietà di dipendenza personalizzate, è necessario tenere conto di questo comportamento ed evitare di inserire altro codice nel wrapper della proprietà, oltre ai metodi del sistema di proprietà <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A>.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisites  
 Questo argomento presuppone la conoscenza delle proprietà di dipendenza sia in qualità di consumer, sia in qualità di autore oltre alla lettura di [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md) e [Proprietà Dependency personalizzate](custom-dependency-properties.md). È inoltre necessario aver letto [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) e [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md).  
  
<a name="implementation"></a>   
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Implementazione del caricatore XAML WPF e prestazioni  
 Per motivi di implementazione, è meno costoso dal punto di vista del calcolo identificare una proprietà come proprietà di dipendenza e accedere al sistema di proprietà <xref:System.Windows.DependencyObject.SetValue%2A> metodo per impostarlo, anziché usare il wrapper della proprietà e il relativo setter. Ciò si verifica in quanto un processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] deve dedurre l'intero modello a oggetti del codice di supporto esclusivamente in base alla conoscenza delle relazioni tra tipi e membri indicate dalla struttura del markup e da varie stringhe.  
  
 Il tipo viene ricercato tramite una combinazione di attributi xmlns e di assembly, ma l'identificazione dei membri, la determinazione di un supporto da impostare come attributo e la risoluzione dei tipi supportati dai valori delle proprietà potrebbero altrimenti richiedere un'ampia Reflection utilizzando <xref:System.Reflection.PropertyInfo>. Poiché le proprietà di dipendenza di un determinato tipo sono accessibili come una tabella di archiviazione tramite il sistema di proprietà, l'implementazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del relativo processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usa questa tabella e deduce che qualsiasi proprietà *ABC* può essere impostata in modo più efficiente da la chiamata di <xref:System.Windows.DependencyObject.SetValue%2A> nell'oggetto che contiene <xref:System.Windows.DependencyObject> tipo derivato, usando l'identificatore della proprietà di dipendenza *ABCProperty*.  
  
<a name="implications"></a>   
## <a name="implications-for-custom-dependency-properties"></a>Implicazioni per le proprietà di dipendenza personalizzate  
 Poiché l'implementazione corrente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del comportamento del processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per l'impostazione delle proprietà ignora completamente i wrapper, non è opportuno inserire logica aggiuntiva nelle definizioni stabilite del wrapper per la proprietà di dipendenza personalizzata. Se si inserisce tale logica nella definizione stabilita, questa non sarà eseguita quando la proprietà viene impostata in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] piuttosto che nel codice.  
  
 Analogamente, anche altri aspetti del processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che ottengono i valori delle proprietà dall'elaborazione [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utilizzano <xref:System.Windows.DependencyObject.GetValue%2A> anziché utilizzare il wrapper. Pertanto, è consigliabile evitare qualsiasi implementazione aggiuntiva nella definizione del `get` oltre la chiamata <xref:System.Windows.DependencyObject.GetValue%2A>.  
  
 L'esempio seguente è una definizione di una proprietà di dipendenza consigliata con wrapper, in cui l'identificatore di proprietà è archiviato come campo `public` `static` `readonly` e le definizioni `get` e `set` non contengono codice oltre ai metodi del sistema di proprietà necessari che definiscono il supporto della proprietà di dipendenza.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Metadati delle proprietà di dipendenza](dependency-property-metadata.md)
- [Proprietà di dipendenza di tipo raccolta](collection-type-dependency-properties.md)
- [Sicurezza delle proprietà di dipendenza](dependency-property-security.md)
- [Modelli di costruttore sicuri per DependencyObject](safe-constructor-patterns-for-dependencyobjects.md)
