---
title: Direttiva x:FactoryMethod
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 436caa9b93467dcf2a0763bcc0962a2beb722315
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45594544"
---
# <a name="xfactorymethod-directive"></a>Direttiva x:FactoryMethod
Specifica un metodo diverso da un costruttore che un processore XAML deve usare per inizializzare un oggetto dopo aver risolto il relativo tipo sottostante.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>Utilizzo dell'attributo XAML, non X:Arguments  
  
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
  
 Sono supportati i metodi statici come i metodi factory. Se `methodname` è un metodo statico `methodname` fornita come una *nomeTipo*. *methodName* combinazione, in cui *typeName* denomina la classe che definisce il metodo factory statico. *typeName* può essere qualificato come prefisso se si fa riferimento a un tipo in un xmlns mappato. *typeName* può essere un tipo diverso da `typeof(object)`.  
  
 Il metodo factory deve essere un metodo dichiarato pubblico del tipo che supporta l'elemento oggetto pertinente.  
  
 Il metodo factory deve restituire un'istanza che può essere assegnata all'oggetto pertinente. I metodi factory non devono mai restituire null.  
  
 `x:Arguments` opera su un principio di corrispondenza migliore per le firme dei metodi factory. Corrispondenza valuta innanzitutto il numero dei parametri. Se è presente più di una corrispondenza possibile per un numero di parametri, tipo di parametro viene quindi valutata e la migliore corrispondenza viene determinata. Se c'è ancora ambiguità dopo questa fase della valutazione, il comportamento del processore XAML è definito.  
  
 Il `x:FactoryMethod` utilizzo dell'elemento non utilizzo dell'elemento di proprietà nel senso tradizionale, perché il markup della direttiva non fa riferimento il tipo dell'elemento oggetto che lo contiene. È previsto che l'utilizzo elemento è meno comune rispetto all'utilizzo dell'attributo. `x:Arguments` (utilizzo di attributo o elemento) può essere utilizzato insieme a `x:FactoryMethod` utilizzo dell'elemento, ma questo non è specificamente illustrato nelle sezioni dell'utilizzo.  
  
 `x:FactoryMethod` come un elemento deve precedere qualsiasi altro elemento proprietà, devono precedere qualsiasi `x:Arguments` anche fornita come elementi e devono precedere qualsiasi testo contenuto/interno. il testo di inizializzazione.  
  
## <a name="see-also"></a>Vedere anche  
 [x:Arguments (direttiva)](../../../docs/framework/xaml-services/x-arguments-directive.md)
