---
title: '{} -Sequenza di escape estensione di Markup'
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
ms.openlocfilehash: a90f6928d68eddd29762e6206769dd7f07704e4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-escape-sequence--markup-extension"></a>{} Sequenza di escape / estensione di Markup
Fornisce la sequenza di escape XAML per i valori di attributo. La sequenza di escape consente i valori successivi nell'attributo deve essere interpretato come un valore letterale.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>Utilizzo della sintassi XAML per elementi proprietà  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|*LiteralValue*|La stringa letterale che segue la sequenza di escape. In genere questa stringa contiene una parentesi graffa aperta o chiusa ({o}).|  
  
## <a name="remarks"></a>Note  
 La sequenza di escape ({}) viene utilizzato in modo che una parentesi graffa aperta ({) può essere utilizzata come carattere letterale in XAML.  
  
 In genere, i reader XAML usano la parentesi graffa di apertura ({}) per indicare il punto di ingresso di un'estensione di markup; tuttavia, vengono innanzitutto controllare il carattere successivo per determinare se è una parentesi graffa di chiusura (}). Solo quando le due parentesi graffe di apertura ({}) sono adiacente, sono possano presi in considerazione una sequenza di escape.  
  
 Se la sequenza di escape viene rilevata, il reader XAML deve elaborare il resto della stringa come stringa. Tuttavia, se la sequenza di escape viene applicata a un membro che dispone di un convertitore di tipi, la stringa potrebbe essere sottoposto a conversione del tipo quando questo viene interpretato da un writer XAML.  
  
 La sequenza di escape non è un'estensione di markup e non è supportata da una classe. Tuttavia, è una convenzione che devono rispettare i reader XAML (inclusi i reader XAML personalizzati).  
  
 Un segno di virgolette (") può essere utilizzato come una sequenza di escape in questo modo. Se è necessario impostare una virgoletta come valore della proprietà per una proprietà noncontent, utilizzare la sintassi degli elementi di proprietà e inserire le virgolette come una stringa all'interno dell'elemento di proprietà oppure utilizzare un'entità carattere XML. Per una proprietà di contenuto, la virgoletta può essere l'intero contenuto.  
  
 La sequenza di escape ({}) è spesso necessario quando si specifica un tipo XML che deve includere un qualificatore dello spazio dei nomi in un percorso in cui potrebbe essere presente un'estensione di markup XAML. Ciò include l'inizio di un valore di attributo XAML in un'estensione di markup, immediatamente dopo il segno di uguale (=). L'esempio seguente mostra le sequenze di escape per uno spazio dei nomi XML che viene visualizzato all'inizio di un valore di attributo XAML.  
  
 [!code-xaml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a>Vedere anche  
 [Convertitori di tipi ed estensioni di markup per XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)  
 [Entità carattere XML e XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)
