---
title: Estensione del markup x:Array
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
caps.latest.revision: "20"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 2cefdee5ca2d1b0a6c79325365aa101d767b6926
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xarray-markup-extension"></a>Estensione del markup x:Array
Fornisce supporto generale per le matrici di oggetti in XAML tramite un'estensione di markup. Corrisponde alla `x:ArrayExtension` tipo XAML in [MS-XAML].  
  
## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`typeName`|Il nome del tipo che il `x:Array` conterrà. `typeName`potrebbe essere (e spesso è) come prefisso per un file XAML le definizioni dei tipi dello spazio dei nomi che contiene il codice XAML.|  
|`arrayContents`|Il contenuto di elementi che è stato assegnato le funzioni intrinseche `ArrayExtension.Items` proprietà. In genere, questi elementi vengono specificati come uno o più elementi di oggetto contenuti all'interno di `x:Array` apertura e chiusura. Gli oggetti specificati di seguito possono essere assegnabile al tipo XAML specificato `typeName`.|  
  
## <a name="remarks"></a>Note  
 `Type`è un attributo obbligatorio per tutti i `x:Array` elementi oggetto. Oggetto `Type` valore del parametro non è necessario utilizzare un `x:Type` estensione di markup; breve nome del tipo è un tipo XAML, che può essere specificato come stringa.  
  
 Nell'implementazione dei servizi XAML di .NET Framework, la relazione tra il tipo di sintassi XAML per gli input e output CLR <xref:System.Type> della matrice creata viene influenzata dal contesto del servizio per le estensioni di markup. L'output <xref:System.Type> è il <xref:System.Xaml.XamlType.UnderlyingType%2A> il tipo di input XAML, dopo avere cercato necessari <xref:System.Xaml.XamlType> in base al contesto dello schema XAML e <xref:System.Windows.Markup.IXamlTypeResolver> servizio fornisce il contesto.  
  
 Durante l'elaborazione, il contenuto della matrice viene assegnato le `ArrayExtension.Items` proprietà intrinseca. Nel <xref:System.Windows.Markup.ArrayExtension> implementazione, è rappresentato da <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.  
  
 Nell'implementazione dei servizi XAML di .NET Framework, la gestione di questa estensione di markup viene definita per la <xref:System.Windows.Markup.ArrayExtension> classe. <xref:System.Windows.Markup.ArrayExtension>non è bloccato e può essere utilizzato come base per un'implementazione dell'estensione di markup per un tipo di matrice personalizzato.  
  
 `x:Array`è che più destinato generale di estensibilità del linguaggio in XAML. Ma `x:Array` può anche essere utile per specificare i valori XAML di determinate proprietà che accettano le raccolte con supporto XAML come contenuto strutturato della proprietà. Ad esempio, è possibile specificare il contenuto di un <xref:System.Collections.IEnumerable> proprietà con un `x:Array` utilizzo.  
  
 `x:Array` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. `x:Array`parzialmente rappresenta un'eccezione alla regola perché invece di fornire la gestione dei valori di attributo alternativo, `x:Array` fornisce la gestione alternativa del contenuto di testo interno. Questo comportamento consente i tipi che potrebbero non essere supportati da un modello di contenuto esistente per essere raggruppati in una matrice e a cui fa riferimento in un secondo momento nel code-behind accedere alla matrice denominata; è possibile chiamare <xref:System.Array> metodi per ottenere i singoli elementi della matrice.  
  
 Tutte le estensioni di markup in XAML utilizzano le parentesi graffe ({,}`)` nella relativa sintassi degli attributi, che è la convenzione mediante il quale un processore XAML riconosce che il valore dell'attributo deve essere elaborato da un'estensione di markup. Per ulteriori informazioni sulle estensioni di markup in generale, vedere [convertitori di tipi ed estensioni di Markup per XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
 In XAML 2009, `x:Array` è definito come un tipo primitivo anziché un'estensione di markup del linguaggio. Per ulteriori informazioni, vedere [tipi incorporati per primitive del linguaggio XAML comuni](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md).  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 In genere, gli elementi di oggetti che popolano un `x:Array` non sono gli elementi esistenti nel [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] spazio dei nomi XAML e richiedono un mapping del prefisso di uno spazio dei nomi XAML non predefinito.  
  
 Ad esempio, ecco una semplice matrice di due stringhe, con la `sys` prefisso (e anche `x`) definiti a livello della matrice.  
  
 [xaml]  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 Per i tipi personalizzati che vengono utilizzati come elementi di matrice, la classe deve inoltre supportare i requisiti per la creazione di un'istanza in XAML come elementi oggetto. Per ulteriori informazioni, vedere [classi XAML e personalizzate per WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Estensioni di markup e XAML WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [Tipi migrati da WPF a System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
