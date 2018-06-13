---
title: Direttiva x:FactoryMethod
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 75225e624abdd3dc0862a04fae409da48b3f0d1e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563415"
---
# <a name="xfactorymethod-directive"></a>Direttiva x:FactoryMethod
Specifica un metodo diverso da un costruttore che un processore XAML deve utilizzare per inizializzare un oggetto dopo aver risolto il relativo tipo sottostante.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>Utilizzo dell'attributo XAML, nessun X:Arguments  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>Utilizzo dell'attributo XAML, X:Arguments come uno o più elementi  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`methodname`|Il nome del metodo di un metodo che chiamano processori XAML per inizializzare l'istanza specificata come stringa `object`. Vedere la sezione Osservazioni.|  
|`oneOrMoreObjectElements`|Uno o più elementi oggetto per gli oggetti che specificano i parametri del metodo factory. L'ordine è significativo; indica l'ordine in cui gli argomenti devono essere passati al metodo factory.|  
  
## <a name="remarks"></a>Note  
 Se `methodname` è un metodo di istanza, non può essere qualificato.  
  
 I metodi come metodi factory statici sono supportati. Se `methodname` è un metodo statico, `methodname` viene fornito come un *typeName*. *NomeMetodo* combinazione, in cui *typeName* denomina la classe che definisce il metodo factory statico. *typeName* può essere qualificato prefisso se si fa riferimento a un tipo in un xmlns mappato. *typeName* può essere un tipo diverso da quello `typeof(``object``)`.  
  
 Il metodo factory deve essere un metodo pubblico dichiarato del tipo che supporta l'elemento oggetto pertinente.  
  
 Il metodo factory deve restituire un'istanza può essere assegnato all'oggetto pertinente. Metodi factory non devono mai restituire null.  
  
 `x:Arguments` opera su un principio di corrispondenza più appropriata per le firme dei metodi factory. Corrispondenza prima valuta il numero dei parametri. Se è presente più di una corrispondenza possibile per un numero di parametri, tipo di parametro viene quindi valutata e la migliore corrispondenza viene determinata. Se è ancora ambiguità dopo questa fase della valutazione, non è definito il comportamento del processore XAML.  
  
 Il `x:FactoryMethod` utilizzo dell'elemento non è utilizzo dell'elemento proprietà in senso tradizionale, perché il markup della direttiva non fa riferimento il tipo dell'elemento oggetto contenitore. È previsto che l'utilizzo elemento è meno comune dell'utilizzo dell'attributo. `x:Arguments` (l'attributo o elemento di utilizzo) può essere usato insieme a `x:FactoryMethod` utilizzo dell'elemento, ma ciò non è specificamente mostrati nelle sezioni utilizzo.  
  
 `x:FactoryMethod` come un elemento deve precedere qualsiasi altro elemento proprietà, devono precedere qualsiasi `x:Arguments` anche fornita come elementi e devono precedere qualsiasi testo contenuto/interno testo di inizializzazione.  
  
## <a name="see-also"></a>Vedere anche  
 [x:Arguments (direttiva)](../../../docs/framework/xaml-services/x-arguments-directive.md)
