---
title: Direttiva x:FactoryMethod
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 586965dd4094e81fd830a09b64604cf33f195630
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053781"
---
# <a name="xfactorymethod-directive"></a>Direttiva x:FactoryMethod
Specifica un metodo diverso da un costruttore che un processore XAML deve usare per inizializzare un oggetto dopo la risoluzione del tipo di supporto.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>Utilizzo degli attributi XAML, nessun x:Arguments  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>Utilizzo degli attributi XAML, x:Arguments come elemento/i  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`methodname`|Nome del metodo di stringa di un metodo che i processori XAML chiamano per inizializzare l' `object`istanza di specificata come. Vedere la sezione Osservazioni.|  
|`oneOrMoreObjectElements`|Uno o più elementi oggetto per gli oggetti che specificano i parametri del metodo factory. L'ordine è significativo. indica l'ordine in cui gli argomenti devono essere passati al metodo factory.|  
  
## <a name="remarks"></a>Note  
 Se `methodname` è un metodo di istanza, non può essere qualificato.  
  
 Sono supportati i metodi statici come metodi factory. Se `methodname` è un metodo statico, `methodname` viene fornito come *typeName*. *combinazione di MethodName* , dove *typeName* denomina la classe che definisce il metodo factory statico. *typeName* può essere qualificato con prefisso se si fa riferimento a un tipo in un xmlns con mapping. *typeName* può essere di un tipo diverso `typeof(object)`da.  
  
 Il metodo factory deve essere un metodo pubblico dichiarato del tipo che esegue il backup dell'elemento oggetto pertinente.  
  
 Il metodo factory deve restituire un'istanza assegnabile all'oggetto pertinente. I metodi factory non devono mai restituire null.  
  
 `x:Arguments`opera su un principio di corrispondenza migliore per le firme dei metodi factory. La corrispondenza valuta prima il numero di parametri. Se è presente più di una corrispondenza possibile per un conteggio di parametri, il tipo di parametro viene valutato e viene determinata la corrispondenza migliore. Se si verifica ancora un'ambiguità dopo questa fase della valutazione, il comportamento del processore XAML non è definito.  
  
 L' `x:FactoryMethod` utilizzo dell'elemento non è l'utilizzo dell'elemento proprietà nel senso tipico, perché il markup della direttiva non fa riferimento al tipo dell'elemento oggetto contenitore. Si prevede che l'utilizzo degli elementi sia meno comune dell'utilizzo dell'attributo. `x:Arguments`(l'utilizzo di attributi o elementi) può essere utilizzato insieme `x:FactoryMethod` all'utilizzo dell'elemento, ma questo non è illustrato in modo specifico nelle sezioni Usage.  
  
 `x:FactoryMethod`Poiché un elemento deve precedere qualsiasi altro elemento di proprietà, deve precedere `x:Arguments` qualsiasi oggetto fornito anche come elemento e deve precedere qualsiasi contenuto/testo interno/di inizializzazione.  
  
## <a name="see-also"></a>Vedere anche

- [x:Arguments (direttiva)](x-arguments-directive.md)
