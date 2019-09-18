---
title: '{}Sequenza di escape-estensione di markup'
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
ms.openlocfilehash: b0646c62a1342eb160d1967e86ac286429013f3c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053871"
---
# <a name="-escape-sequence--markup-extension"></a>{} Sequenza di escape/Estensione di markup
Fornisce la sequenza di escape XAML per i valori di attributo. La sequenza di escape consente di interpretare i valori successivi nell'attributo come valore letterale.  
  
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
|*literalValue*|Stringa letterale che segue la sequenza di escape. Questa stringa contiene in genere una parentesi graffa di apertura o di chiusura ({o}).|  
  
## <a name="remarks"></a>Note  
 Viene utilizzata la sequenza{}di escape () in modo che una parentesi graffa aperta ({) possa essere utilizzata come carattere letterale in XAML.  
  
 I reader XAML usano in genere la parentesi graffa aperta ({) per indicare il punto di ingresso di un'estensione di markup. Tuttavia, prima di tutto controllano il carattere successivo per determinare se si tratta di una parentesi graffa di chiusura (}). Solo quando le due parentesi graffe ({}) sono adiacenti, sono considerate una sequenza di escape.  
  
 Se viene rilevata la sequenza di escape, il reader XAML deve elaborare il resto della stringa sotto forma di stringa. Tuttavia, se la sequenza di escape viene applicata a un membro che dispone di un convertitore di tipi, la stringa potrebbe subire la conversione del tipo quando viene interpretata da un writer XAML.  
  
 La sequenza di escape non è un'estensione di markup e non è supportata da una classe. Tuttavia, è una convenzione che i reader XAML (compresi i lettori XAML personalizzati) devono rispettare.  
  
 In questo modo non è possibile usare come sequenza di escape le virgolette ("). Se è necessario impostare una virgoletta come valore della proprietà per una proprietà non di contenuto, utilizzare la sintassi dell'elemento proprietà e inserire le virgolette come una stringa all'interno dell'elemento Property oppure utilizzare un'entità carattere XML. Per una proprietà di contenuto, le virgolette possono essere l'intero contenuto.  
  
 La sequenza di escape{}() è spesso obbligatoria quando si specifica un tipo XML che deve includere un qualificatore dello spazio dei nomi in una posizione in cui può essere visualizzata un'estensione di markup XAML. Questo include l'inizio di un valore di attributo XAML e in un'estensione di markup immediatamente dopo un segno di uguale (=). Nell'esempio seguente vengono illustrate le sequenze di escape per uno spazio dei nomi XML che viene visualizzato all'inizio di un valore di attributo XAML.  
  
 [!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a>Vedere anche

- [Convertitori di tipi ed estensioni di markup per XAML](type-converters-and-markup-extensions-for-xaml.md)
- [Entità carattere XML e XAML](xml-character-entities-and-xaml.md)
