---
title: Direttiva x:FactoryMethod
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 5e864b6f5d664b079036a5d915e2f6f81b83639f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071535"
---
# <a name="xfactorymethod-directive"></a>Direttiva x:FactoryMethod
Specifica un metodo diverso da un costruttore che un processore XAML deve utilizzare per inizializzare un oggetto dopo la risoluzione del tipo di supporto.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>Utilizzo degli attributi XAML, senza x:ArgumentsXAML Attribute Usage, no x:Arguments  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>Utilizzo degli attributi XAML, x:Arguments come elemento/iXAML Attribute Usage, x:Arguments as Element(s)  
  
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
|`methodname`|Nome del metodo stringa di un metodo chiamato dai `object`processori XAML per inizializzare l'istanza specificata come . Vedere la sezione Osservazioni.|  
|`oneOrMoreObjectElements`|Uno o più elementi oggetto per gli oggetti che specificano i parametri del metodo factory. L'ordine è significativo; indica l'ordine in cui gli argomenti devono essere passati al metodo factory.|  
  
## <a name="remarks"></a>Osservazioni  
 Se `methodname` è un metodo di istanza, non può essere qualificato.  
  
 Sono supportati i metodi statici come metodi factory. Se `methodname` è un `methodname` metodo statico, `typeName.methodName` viene `typeName` fornito come combinazione, in cui denomina la classe che definisce il metodo factory statico. `typeName`può essere qualificato con prefisso se si fa riferimento a un tipo in un xmlns mappato. `typeName`può essere di `typeof(object)`tipo diverso da .  
  
 Il metodo factory deve essere un metodo pubblico dichiarato del tipo che supporta l'elemento oggetto pertinente.  
  
 Il metodo factory deve restituire un'istanza assegnabile all'oggetto pertinente. I metodi factory non devono mai restituire null.  
  
 `x:Arguments`opera su un principio di migliore corrispondenza per le firme dei metodi factory. La corrispondenza valuta prima il conteggio dei parametri. Se esiste più di una corrispondenza possibile per un conteggio di parametri, il tipo di parametro viene quindi valutato e viene determinata la corrispondenza migliore. Se c'è ancora ambiguità dopo questa fase di valutazione, il comportamento del processore XAML non è definito.  
  
 L'utilizzo `x:FactoryMethod` dell'elemento non è l'utilizzo dell'elemento proprietà nel senso tipico, perché il markup della direttiva non fa riferimento al tipo dell'elemento oggetto contenitore. Si prevede che l'utilizzo degli elementi sia meno comune dell'utilizzo degli attributi. `x:Arguments`(utilizzo di attributi o elementi) `x:FactoryMethod` può essere utilizzato insieme all'utilizzo dell'elemento, ma ciò non è illustrato in modo specifico nelle sezioni di utilizzo.  
  
 `x:FactoryMethod`come elemento deve precedere qualsiasi altro elemento `x:Arguments` proprietà, deve precedere qualsiasi fornito anche come elementi e deve precedere qualsiasi testo di contenuto/testo interno/inizializzazione.  
  
## <a name="see-also"></a>Vedere anche

- [Direttiva x:Arguments](xarguments-directive.md)
