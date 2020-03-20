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
ms.openlocfilehash: de8050e582f5b1a5a288c350c179cfa24fb5471c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186246"
---
# <a name="xaml-loading-and-dependency-properties"></a>Caricamento XAML e proprietà di dipendenza
L'implementazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] corrente del relativo processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dipende implicitamente dalle proprietà di dipendenza. Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore utilizza i metodi del sistema [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] di proprietà per le proprietà di dipendenza durante il caricamento di attributi binari ed elaborando attributi che sono proprietà di dipendenza. Ciò consente di ignorare in modo efficace i wrapper della proprietà. Quando si implementano proprietà di dipendenza personalizzate, è necessario tenere conto di questo comportamento <xref:System.Windows.DependencyObject.GetValue%2A> ed <xref:System.Windows.DependencyObject.SetValue%2A>evitare di inserire altro codice nel wrapper della proprietà diverso dai metodi del sistema di proprietà e .  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisites  
 Questo argomento presuppone la conoscenza delle proprietà di dipendenza sia in qualità di consumer, sia in qualità di autore oltre alla lettura di [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md) e [Proprietà Dependency personalizzate](custom-dependency-properties.md). È inoltre necessario aver letto [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) e [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md).  
  
<a name="implementation"></a>
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Implementazione del caricatore XAML WPF e prestazioni  
 Per motivi di implementazione, è meno costoso dal punto di vista <xref:System.Windows.DependencyObject.SetValue%2A> del calcolo identificare una proprietà come proprietà di dipendenza e accedere al metodo del sistema di proprietà per impostarla, anziché usare il wrapper della proprietà e il relativo setter. Ciò si verifica in quanto un processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] deve dedurre l'intero modello a oggetti del codice di supporto esclusivamente in base alla conoscenza delle relazioni tra tipi e membri indicate dalla struttura del markup e da varie stringhe.  
  
 Il tipo viene cercato tramite una combinazione di xmlns e attributi di assembly, ma identificando i membri, determinando quale potrebbe supportare l'impostazione come attributo e risolvendo i tipi supportati dai valori di proprietà altrimenti richiederebbe un'ampia reflection mediante <xref:System.Reflection.PropertyInfo>. Poiché le proprietà di dipendenza su un determinato tipo sono [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] accessibili [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] come tabella di archiviazione tramite il sistema di proprietà, l'implementazione <xref:System.Windows.DependencyObject> del processore utilizza questa tabella e deduce che qualsiasi proprietà *specificata ABC* può essere impostata in modo più efficiente chiamando <xref:System.Windows.DependencyObject.SetValue%2A> il tipo derivato contenitore, utilizzando l'identificatore della proprietà di dipendenza *ABCProperty*.  
  
<a name="implications"></a>
## <a name="implications-for-custom-dependency-properties"></a>Implicazioni per le proprietà di dipendenza personalizzate  
 Poiché l'implementazione corrente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del comportamento del processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per l'impostazione delle proprietà ignora completamente i wrapper, non è opportuno inserire logica aggiuntiva nelle definizioni stabilite del wrapper per la proprietà di dipendenza personalizzata. Se si inserisce tale logica nella definizione stabilita, questa non sarà eseguita quando la proprietà viene impostata in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] piuttosto che nel codice.  
  
 Analogamente, anche altri [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] aspetti del processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che <xref:System.Windows.DependencyObject.GetValue%2A> ottengono valori di proprietà dall'elaborazione vengono utilizzati anziché il wrapper. Pertanto, è inoltre necessario evitare `get` qualsiasi <xref:System.Windows.DependencyObject.GetValue%2A> implementazione aggiuntiva nella definizione oltre la chiamata.  
  
 L'esempio seguente è una definizione di proprietà di dipendenza consigliata con wrapper, in cui l'identificatore `public` `static` `readonly` di proprietà viene archiviato come campo e le `get` definizioni e `set` non contengono codice oltre ai metodi del sistema di proprietà necessari che definiscono il backup della proprietà di dipendenza.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Metadati della proprietà di dipendenza](dependency-property-metadata.md)
- [Proprietà di dipendenza di tipo raccolta](collection-type-dependency-properties.md)
- [Sicurezza della proprietà di dipendenza](dependency-property-security.md)
- [Modelli di costruttore sicuri per DependencyObject](safe-constructor-patterns-for-dependencyobjects.md)
