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
ms.openlocfilehash: 28e121e73ad4bd8ab70aed5f651418eb309b0c03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="xaml-loading-and-dependency-properties"></a>Caricamento XAML e proprietà di dipendenza
L'implementazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] corrente del relativo processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dipende implicitamente dalle proprietà di dipendenza. Il processore [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usa metodi del sistema di proprietà per le proprietà di dipendenza al momento del caricamento del codice [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] binario e dell'elaborazione di attributi che sono proprietà di dipendenza. Ciò consente di ignorare in modo efficace i wrapper della proprietà. Quando si implementa una proprietà di dipendenza personalizzata, è necessario tenere presente questo comportamento e consigliabile evitare di inserire qualsiasi altro codice nel wrapper della proprietà oltre ai metodi di sistema di proprietà <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A>.  
  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento presuppone la conoscenza delle proprietà di dipendenza sia in qualità di consumer, sia in qualità di autore oltre alla lettura di [Cenni preliminari sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) e [Proprietà Dependency personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md). È inoltre necessario aver letto [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) e [Descrizione dettagliata della sintassi XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
<a name="implementation"></a>   
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Implementazione del caricatore XAML WPF e prestazioni  
 Per motivi di implementazione, è meno onerosa identificare una proprietà come proprietà di dipendenza e accedere al sistema di proprietà <xref:System.Windows.DependencyObject.SetValue%2A> metodo per impostare, anziché tramite il wrapper della proprietà e i relativi set. Ciò si verifica in quanto un processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] deve dedurre l'intero modello a oggetti del codice di supporto esclusivamente in base alla conoscenza delle relazioni tra tipi e membri indicate dalla struttura del markup e da varie stringhe.  
  
 Il tipo viene cercato tramite una combinazione di attributi xmlns e assembly, ma che identifica i membri, determinare quale potrebbe essere supportato da impostare come un attributo, e la risoluzione dei tipi supportano i valori delle proprietà in caso contrario richiedono la reflection estesa utilizzando <xref:System.Reflection.PropertyInfo>. Poiché le proprietà di dipendenza su un determinato tipo sono accessibili come tabella di archiviazione tramite il sistema di proprietà, il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementazione del relativo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore utilizzato in questa tabella e viene dedotto da qualsiasi data proprietà *ABC* può essere impostata in modo più efficiente chiamando <xref:System.Windows.DependencyObject.SetValue%2A> nel contenitore <xref:System.Windows.DependencyObject> derivato tipo usando l'identificatore della proprietà di dipendenza *ProprietàABC*.  
  
<a name="implications"></a>   
## <a name="implications-for-custom-dependency-properties"></a>Implicazioni per le proprietà di dipendenza personalizzate  
 Poiché l'implementazione corrente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del comportamento del processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per l'impostazione delle proprietà ignora completamente i wrapper, non è opportuno inserire logica aggiuntiva nelle definizioni stabilite del wrapper per la proprietà di dipendenza personalizzata. Se si inserisce tale logica nella definizione stabilita, questa non sarà eseguita quando la proprietà viene impostata in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] piuttosto che nel codice.  
  
 Analogamente, gli altri aspetti del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore che ottengono i valori delle proprietà da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utilizzare anche l'elaborazione <xref:System.Windows.DependencyObject.GetValue%2A> anziché usare quella wrapper. Pertanto, evitare anche qualsiasi implementazione aggiuntiva nella `get` definizione oltre il <xref:System.Windows.DependencyObject.GetValue%2A> chiamare.  
  
 L'esempio seguente è una definizione di una proprietà di dipendenza consigliata con wrapper, in cui l'identificatore di proprietà è archiviato come campo `public` `static` `readonly` e le definizioni `get` e `set` non contengono codice oltre ai metodi del sistema di proprietà necessari che definiscono il supporto della proprietà di dipendenza.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Metadati delle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)  
 [Proprietà di dipendenza di tipo raccolta](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)  
 [Sicurezza delle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-property-security.md)  
 [Modelli di costruttore sicuri per DependencyObject](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)
