---
title: estensione di markup x:Reference
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03b63cb40e57223d5c66c03fb60780689cd6c925
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
 `x:Reference`fornisce supporto a livello di linguaggio XAML per un concetto di riferimento di elemento che è stato implementato in caso contrario in Framework specifici, ad esempio WPF.  
  
## <a name="xreference-and-wpf"></a>X:Reference e WPF  
 In WPF e XAML 2006, i riferimenti dell'elemento vengono indirizzati mediante la funzionalità a livello di framework di <xref:System.Windows.Data.Binding.ElementName%2A> associazione. Per la maggior parte delle applicazioni WPF e scenari, <xref:System.Windows.Data.Binding.ElementName%2A> deve ancora essere utilizzata l'associazione. Eccezioni a questa Guida generale potrebbero includere casi in cui sono presenti contesto dei dati o altre considerazioni di ambito che causa è consigliabile eseguire l'associazione dati e la compilazione del markup non è coinvolto.  
  
 `x:Reference`è un costrutto definito in XAML 2009. In WPF è possibile usare le funzionalità di XAML 2009, ma solo per il codice XAML non compilato dal markup WPF. Il codice XAML compilato dal markup e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.
