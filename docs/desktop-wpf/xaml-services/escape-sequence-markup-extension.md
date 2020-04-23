---
title: '{}Sequenza di escape - Estensione di markup'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: f84243994557d76fa52d72b060a1ba35460e98b0
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071745"
---
# <a name="-escape-sequence--markup-extension"></a>{}Sequenza di escape / estensione di markup

Fornisce la sequenza di escape XAML per i valori degli attributi. La sequenza di escape consente ai valori successivi nell'attributo di essere interpretati come valore letterale.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a>Utilizzo della sintassi XAML per elementi proprietà

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|*valore letteraleValore*|Stringa letterale che segue la sequenza di escape. In genere questa stringa contiene una parentesi graffa aperta o chiusa (Sezione o ) .|

## <a name="remarks"></a>Osservazioni

La sequenza{}di escape ( ) viene utilizzata in modo che sia possibile utilizzare una parentesi graffa aperta ( ) come carattere letterale in XAML.

I lettori XAML usano in genere la parentesi graffa aperta per indicare il punto di ingresso di un'estensione di markup; tuttavia, controllano innanzitutto il carattere successivo per determinare se si tratta di una parentesi graffa di chiusura (). Solo quando le due{}parentesi graffe ( ) sono adiacenti, vengono considerate una sequenza di escape.

Se viene rilevata la sequenza di escape, il reader XAML deve elaborare il resto della stringa come stringa. Tuttavia, se la sequenza di escape viene applicata a un membro che dispone di un convertitore di tipi, la stringa potrebbe subire la conversione del tipo quando viene interpretata da un writer XAML.

La sequenza di escape non è un'estensione di markup e non è supportata da una classe. Tuttavia, è una convenzione che i lettori XAML (inclusi i reader XAML personalizzati) devono rispettare.

Le virgolette (") non possono essere utilizzate come sequenza di escape in questo modo. Se è necessario impostare una virgoletta come valore di proprietà per una proprietà non di contenuto, utilizzare la sintassi degli elementi proprietà e inserire le virgolette come stringa all'interno dell'elemento proprietà oppure utilizzare un'entità carattere XML. Per una proprietà di contenuto, le virgolette possono essere l'intero contenuto.

La sequenza{}di escape ( ) è spesso necessaria quando si specifica un tipo XML che deve includere un qualificatore dello spazio dei nomi in una posizione in cui potrebbe essere visualizzata un'estensione di markup XAML. Questa posizione include l'inizio di un valore dell'attributo XAML e in un'estensione di markup immediatamente dopo un segno di uguale (Sezione ). Nell'esempio seguente vengono illustrate le sequenze di escape per uno spazio dei nomi XML visualizzato all'inizio di un valore di attributo XAML.

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a>Vedere anche

- [Convertitori di tipi ed estensioni di markup per XAML](type-converters-and-markup-extensions.md)
- [Entità carattere XML e XAML](xml-character-entities.md)
