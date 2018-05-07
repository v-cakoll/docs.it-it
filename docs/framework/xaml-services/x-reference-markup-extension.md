---
title: estensione di markup x:Reference
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: 960f5c0e4192df72090c1a571dfc2fc5e3fd8ba3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="xreference-markup-extension"></a>estensione di markup x:Reference
Fa riferimento a un'istanza che è dichiarata in un' posizione nel markup XAML. Il riferimento si riferisce a un elemento `x:Name`.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object property="{x:Reference instancexName}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto  
  
```xaml  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`instancexName`|Il `x:Name` valore (o valore del <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-proprietà identificata) dell'istanza di riferimento.|  
  
## <a name="remarks"></a>Note  
 `x:Reference` fornisce supporto a livello di linguaggio XAML per un concetto di riferimento di elemento che è stato implementato in caso contrario, nel framework specifici, ad esempio WPF.  
  
## <a name="xreference-and-wpf"></a>X:Reference e WPF  
 In WPF e XAML 2006, i riferimenti dell'elemento vengono indirizzati mediante la funzionalità a livello di framework di <xref:System.Windows.Data.Binding.ElementName%2A> associazione. Per la maggior parte delle applicazioni WPF e scenari, <xref:System.Windows.Data.Binding.ElementName%2A> deve ancora essere utilizzata l'associazione. Eccezioni a questa Guida generale potrebbero includere casi in cui sono presenti contesto dei dati o altre considerazioni di ambito che causa è consigliabile eseguire l'associazione dati e la compilazione del markup non è coinvolto.  
  
 `x:Reference` è un costrutto definito in XAML 2009. In WPF è possibile usare le funzionalità di XAML 2009, ma solo per il codice XAML non compilato dal markup WPF. Il codice XAML compilato dal markup e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.
