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
ms.openlocfilehash: ed608a658b5077a20ed56419c4ac731641610e3d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373075"
---
# <a name="xaml-loading-and-dependency-properties"></a>Caricamento XAML e proprietà di dipendenza
L'implementazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] corrente del relativo processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dipende implicitamente dalle proprietà di dipendenza. Il processore [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usa metodi del sistema di proprietà per le proprietà di dipendenza al momento del caricamento del codice [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] binario e dell'elaborazione di attributi che sono proprietà di dipendenza. Ciò consente di ignorare in modo efficace i wrapper della proprietà. Quando si implementano proprietà di dipendenza personalizzate, è necessario tenere presente questo comportamento ed evitare di inserire qualsiasi altro codice nel wrapper della proprietà oltre ai metodi di sistema di proprietà <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A>.  
  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento presuppone la conoscenza delle proprietà di dipendenza sia in qualità di consumer, sia in qualità di autore oltre alla lettura di [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md) e [Proprietà Dependency personalizzate](custom-dependency-properties.md). È inoltre necessario aver letto [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md) e [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md).  
  
<a name="implementation"></a>   
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Implementazione del caricatore XAML WPF e prestazioni  
 Per motivi di implementazione, è meno dispendiosa identificare una proprietà come proprietà di dipendenza e accedere al sistema di proprietà <xref:System.Windows.DependencyObject.SetValue%2A> metodo per impostare, anziché tramite il wrapper della proprietà e il relativo setter. Ciò si verifica in quanto un processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] deve dedurre l'intero modello a oggetti del codice di supporto esclusivamente in base alla conoscenza delle relazioni tra tipi e membri indicate dalla struttura del markup e da varie stringhe.  
  
 Il tipo viene ricercato tramite una combinazione di attributi xmlns e assembly, ma che identifica i membri, che determina quale possono supportare impostato come un attributo, e la risoluzione dei tipi supportano i valori delle proprietà in caso contrario, richiedono la reflection estesa usando <xref:System.Reflection.PropertyInfo>. Poiché le proprietà di dipendenza in un determinato tipo sono accessibili come una tabella di archiviazione tramite il sistema di proprietà, il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementazione di relativo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore utilizza questa tabella e deduce che qualsiasi proprietà specificata *ABC* può essere impostata in modo più efficiente chiamando <xref:System.Windows.DependencyObject.SetValue%2A> sul contenitore <xref:System.Windows.DependencyObject> derivato tipo usando l'identificatore di proprietà di dipendenza *ProprietàABC*.  
  
<a name="implications"></a>   
## <a name="implications-for-custom-dependency-properties"></a>Implicazioni per le proprietà di dipendenza personalizzate  
 Poiché l'implementazione corrente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del comportamento del processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per l'impostazione delle proprietà ignora completamente i wrapper, non è opportuno inserire logica aggiuntiva nelle definizioni stabilite del wrapper per la proprietà di dipendenza personalizzata. Se si inserisce tale logica nella definizione stabilita, questa non sarà eseguita quando la proprietà viene impostata in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] piuttosto che nel codice.  
  
 Allo stesso modo, altri aspetti del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore che i valori delle proprietà da ottenere [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Usa anche l'elaborazione <xref:System.Windows.DependencyObject.GetValue%2A> piuttosto che il wrapper. Pertanto, è anche consigliabile evitare qualsiasi implementazione aggiuntiva nella `get` definition oltre il <xref:System.Windows.DependencyObject.GetValue%2A> chiamare.  
  
 L'esempio seguente è una definizione di una proprietà di dipendenza consigliata con wrapper, in cui l'identificatore di proprietà è archiviato come campo `public` `static` `readonly` e le definizioni `get` e `set` non contengono codice oltre ai metodi del sistema di proprietà necessari che definiscono il supporto della proprietà di dipendenza.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
- [Metadati delle proprietà di dipendenza](dependency-property-metadata.md)
- [Proprietà di dipendenza di tipo raccolta](collection-type-dependency-properties.md)
- [Sicurezza delle proprietà di dipendenza](dependency-property-security.md)
- [Modelli di costruttore sicuri per DependencyObject](safe-constructor-patterns-for-dependencyobjects.md)
