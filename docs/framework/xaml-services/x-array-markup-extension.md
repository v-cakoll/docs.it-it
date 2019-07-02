---
title: Estensione del markup x:Array
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: 8acb732841aa7aaaad3e8fdd2cf2962ff44dd60b
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506064"
---
# <a name="xarray-markup-extension"></a>Estensione del markup x:Array
Fornisce il supporto generale per le matrici di oggetti in XAML tramite un'estensione di markup. Corrisponde al `x:ArrayExtension` tipo XAML in [MS-XAML].  
  
## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto  
  
```xaml
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`typeName`|Il nome del tipo che il `x:Array` conterrà. `typeName` potrebbe essere (e spesso è) come prefisso per un XAML definizioni di tipi dello spazio dei nomi che contiene il XAML.|  
|`arrayContents`|Il contenuto degli elementi assegnato per la funzione intrinseca `ArrayExtension.Items` proprietà. In genere, questi elementi vengono specificati come uno o più elementi di oggetti contenuti all'interno di `x:Array` di apertura e chiusura di tag. Gli oggetti specificati di seguito possono essere assegnabile al tipo di XAML specificato in `typeName`.|  
  
## <a name="remarks"></a>Note  
 `Type` è un attributo obbligatorio per tutti i `x:Array` elementi oggetto. Oggetto `Type` valore del parametro non è necessario usare un `x:Type` estensione di markup; breve nome del tipo è un tipo XAML, che può essere specificato sotto forma di stringa.  
  
 Nell'implementazione dei servizi XAML di .NET Framework, la relazione tra il tipo XAML di input e output CLR <xref:System.Type> della matrice creata è influenzata dal contesto del servizio per le estensioni di markup. L'output <xref:System.Type> è il <xref:System.Xaml.XamlType.UnderlyingType%2A> del tipo XAML di input, dopo aver cercato le necessarie <xref:System.Xaml.XamlType> basato sul contesto dello schema XAML e <xref:System.Windows.Markup.IXamlTypeResolver> service fornisce il contesto.  
  
 Durante l'elaborazione, il contenuto della matrice è assegnato al `ArrayExtension.Items` proprietà intrinseca. Nel <xref:System.Windows.Markup.ArrayExtension> implementazione, è rappresentato dal <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.  
  
 Nell'implementazione di servizi XAML di .NET Framework, la gestione di questa estensione di markup viene definita per il <xref:System.Windows.Markup.ArrayExtension> classe. <xref:System.Windows.Markup.ArrayExtension> non è bloccato e può essere usato come base per un'implementazione dell'estensione di markup per un tipo di matrice personalizzata.  
  
 `x:Array` è che più destinato generale di estendibilità del linguaggio XAML. Ma `x:Array` può anche essere utile per specificare i valori di determinate proprietà che accettano le raccolte supportate da XAML come contenuto della proprietà strutturato XAML. Ad esempio, è possibile specificare il contenuto di un <xref:System.Collections.IEnumerable> proprietà con un `x:Array` utilizzo.  
  
 `x:Array` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. `x:Array` infatti parzialmente un'eccezione alla regola invece di fornire la gestione dei valori di attributo alternativo, `x:Array` fornisce la gestione alternativa del contenuto di testo interno. Questo comportamento consente a tipi che potrebbero non essere supportati da un modello di contenuto esistente per essere raggruppate in una matrice e fa riferimento in un secondo momento nel code-behind accesso all'array denominato; è possibile chiamare <xref:System.Array> metodi per ottenere i singoli elementi della matrice.  
  
 Tutte le estensioni di markup in XAML usano le parentesi graffe ({,} `)` nella sintassi degli attributi, che è la convenzione mediante il quale un processore XAML riconosce che il valore dell'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni sulle estensioni di markup in generale, vedere [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions-for-xaml.md).  
  
 XAML 2009, `x:Array` viene definito come un tipo primitivo invece di un'estensione di markup del linguaggio. Per altre informazioni, vedere [i tipi nativi per primitive del linguaggio XAML comuni](built-in-types-for-common-xaml-language-primitives.md).  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 In genere, gli elementi di oggetti che popolano un `x:Array` non sono gli elementi esistenti nel [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] dello spazio dei nomi XAML e richiede un mapping del prefisso di uno spazio dei nomi XAML non predefinito.  
  
 Ad esempio, ecco una semplice matrice di due stringhe, con la `sys` prefisso (e anche `x`) definiti a livello della matrice.  
  
```xaml
<x:Array Type="sys:String"
         xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
         xmlns:sys="clr-namespace:System;assembly=mscorlib">
    <sys:String>Hello</sys:String>
    <sys:String>World</sys:String>
</x:Array>
```
  
 Per i tipi personalizzati che vengono utilizzati come elementi della matrice, la classe deve anche supportare i requisiti per la creazione di un'istanza in XAML come elementi oggetto. Per altre informazioni, vedere [XAML e classi personalizzate per WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md).  
  
## <a name="see-also"></a>Vedere anche

- [Estensioni di markup e XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [Tipi migrati da WPF a System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
