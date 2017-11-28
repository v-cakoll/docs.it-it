---
title: Estensione del markup x:Null
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- Null
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
caps.latest.revision: "20"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: a60d74bdf3343d02eaf912ac7700f36a649f659c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xnull-markup-extension"></a>Estensione del markup x:Null
Specifica `null` come valore per un membro XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>Note  
 La parola chiave per un riferimento null in [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] e [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] è null. Il [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] è la parola chiave per un riferimento null `Nothing`, ma si utilizza sempre `{x:Null}` come l'utilizzo XAML indipendentemente dal linguaggio di codice è possibile associare il codice XAML.  
  
 Il `x:Null` estensione di markup non contiene proprietà impostabili.  
  
 Un utilizzo null spesso è associato l'esposizione del membro XAML di un tipo CLR <xref:System.Nullable%601> valore.  
  
 Il `x:Null` estensione di markup, ad esempio tutte le estensioni di markup XAML, utilizza le parentesi graffe (`{,}`) per eseguire l'escape la gestione dei valori di attributo affinché siano diversi da valori letterali o riferimenti del gestore eventi. Sintassi dell'attributo è in genere utilizzati con questa estensione di markup. La sintassi degli elementi oggetto `<x:Null />` è tecnicamente possibile, ma viene usato raramente perché il `x:Null` estensione di markup non dispone di parametri posizionali o gli argomenti di costruzione.  
  
 Per informazioni sulle estensioni di markup, vedere [le estensioni di Markup e XAML WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 Nei servizi XAML di .NET Framework, la gestione di questa estensione di markup viene definita per la <xref:System.Windows.Markup.NullExtension> classe.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 Si noti che `null` non è necessariamente il valore iniziale non impostato per una proprietà di dipendenza di tipo riferimento. Il valore predefinito iniziale può variare per ogni proprietà di dipendenza e può essere basato sui metadati specifici della proprietà. Molte proprietà di dipendenza non accettano `null` come valore, tramite markup o codice a causa delle implementazioni dei callback di convalida. Per ulteriori informazioni sulle proprietà di dipendenza, vedere [Cenni preliminari sulle proprietà di dipendenza](../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.DependencyProperty.UnsetValue>  
 [Cenni preliminari su XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Estensioni di markup e XAML WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
