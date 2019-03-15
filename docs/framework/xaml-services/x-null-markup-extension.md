---
title: Estensione del markup x:Null
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: 34a2de71bec9b0929070aa908741de38b5904643
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2019
ms.locfileid: "58029371"
---
# <a name="xnull-markup-extension"></a>Estensione del markup x:Null
Specifica `null` come valore per un membro XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>Note  
 La parola chiave per un riferimento null in C# e [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] è null. La parola chiave Microsoft Visual Basic per un riferimento null viene `Nothing`, ma è sempre usare `{x:Null}` come l'utilizzo XAML indipendentemente dal linguaggio di code-behind è associare il XAML.  
  
 Il `x:Null` estensione di markup non contiene proprietà impostabili.  
  
 Un utilizzo di null è spesso associato all'esposizione del membro XAML di un tipo CLR <xref:System.Nullable%601> valore.  
  
 Il `x:Null` estensione di markup, come tutte le estensioni di markup XAML, Usa le parentesi graffe (`{,}`) per eseguire l'escape la gestione di valori di attributo sia diverso da valori letterali o i riferimenti del gestore eventi. Sintassi dell'attributo è in genere usati con questa estensione di markup. La sintassi degli elementi oggetto `<x:Null />` sia tecnicamente possibile, ma viene usato raramente perché il `x:Null` estensione di markup non dispone di parametri posizionali o argomenti di costruzione.  
  
 Per informazioni sulle estensioni di markup, vedere [estensioni di Markup e XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 Nei servizi XAML di .NET Framework, la gestione di questa estensione di markup viene definita per il <xref:System.Windows.Markup.NullExtension> classe.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 Si noti che `null` non è necessariamente il valore iniziale non impostato per una proprietà di dipendenza di tipo riferimento. Il valore predefinito iniziale può variare per ogni proprietà di dipendenza e può essere basato su proprietà specifiche metadati. Molte proprietà di dipendenza non accettano `null` come valore, tramite markup o codice a causa delle implementazioni dei callback di convalida. Per altre informazioni sulle proprietà di dipendenza, vedere [Cenni preliminari sulle proprietà di dipendenza](../wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Cenni preliminari su XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
- [Estensioni di markup e XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
