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
ms.openlocfilehash: ff82b0bfc1983240431e582dbd78778dc4469241
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459941"
---
# <a name="xnull-markup-extension"></a>Estensione del markup x:Null
Specifica `null` come valore per un membro XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>Note  
 La parola chiave per un riferimento null C# in C++ e è null. La parola chiave Microsoft Visual Basic per un riferimento null è `Nothing`, ma si usa sempre `{x:Null}` come utilizzo di XAML indipendentemente dal linguaggio code-behind associato a XAML.  
  
 Il `x:Null` estensione di markup non dispone di proprietà impostabili.  
  
 Un utilizzo null è spesso associato all'esposizione del membro XAML di un valore di <xref:System.Nullable%601> CLR.  
  
 Il `x:Null` estensione di markup, come tutte le estensioni di markup XAML, USA le parentesi graffe (`{,}`) per l'escape della gestione dei valori di attributo in modo che non siano valori letterali o riferimenti al gestore eventi. La sintassi degli attributi è la sintassi utilizzata più di frequente con questa estensione di markup. Una sintassi dell'elemento oggetto `<x:Null />` è tecnicamente possibile, ma viene usata raramente perché l'estensione di markup `x:Null` non contiene parametri posizionali o argomenti di costruzione.  
  
 Per informazioni sulle estensioni di markup, vedere [estensioni di markup e XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 In .NET Framework servizi XAML, la gestione di questa estensione di markup viene definita dalla classe <xref:System.Windows.Markup.NullExtension>.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF  
 Si noti che `null` non è necessariamente il valore iniziale non impostato per una proprietà di dipendenza di tipo riferimento. Il valore predefinito iniziale può variare per ogni proprietà di dipendenza e può essere basato su metadati specifici della proprietà. Molte proprietà di dipendenza non accettano `null` come valore, tramite markup o codice a causa delle implementazioni di callback di convalida. Per ulteriori informazioni sulle proprietà di dipendenza, vedere [Cenni preliminari sulle proprietà di dipendenza](../wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Cenni preliminari su XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
