---
title: Direttiva x:Arguments
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 5ec6e192688e1065ea847db6c175ad9da0e743fe
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071591"
---
# <a name="xarguments-directive"></a>Direttiva x:Arguments

Crea pacchetti di argomenti di costruzione per una dichiarazione di elemento oggetto costruttore senza parametri in XAML o per una dichiarazione di oggetto metodo factory.

## <a name="xaml-element-usage-nonparameterless-constructor"></a>Utilizzo degli elementi XAML (costruttore senza parametri)XAML Element Usage (Nonparameterless constructor)

```xaml
<object ...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-element-usage-factory-method"></a>Utilizzo degli elementi XAML (metodo factory)XAML Element Usage (factory method)

```xaml
<object x:FactoryMethod="methodName"...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`oneOrMoreObjectElements`|Uno o più elementi oggetto che specificano gli argomenti da passare al costruttore non senza parametri di backup o al metodo factory.<br /><br /> L'utilizzo tipico consiste nell'utilizzare il testo di inizializzazione all'interno degli elementi oggetto per specificare i valori effettivi dell'argomento. Vedere la sezione Esempi.<br /><br /> L'ordine degli elementi è significativo. I tipi XAML nell'ordine devono corrispondere ai tipi e all'ordine dei tipi del costruttore di supporto o dell'overload del metodo factory.|
|`methodName`|Nome del metodo factory che `x:Arguments` deve elaborare gli argomenti.|

## <a name="dependencies"></a>Dependencies

`x:FactoryMethod`possibile modificare l'ambito `x:Arguments` e il comportamento laddove applicati.

Se `x:FactoryMethod` non viene `x:Arguments` specificato alcun valore, si applica alle firme alternative (non predefinite) dei costruttori di backup.

Se `x:FactoryMethod` viene `x:Arguments` specificato, si applica a un overload del metodo denominato.

## <a name="remarks"></a>Osservazioni

XAML 2006 può supportare l'inizializzazione non predefinita tramite testo di inizializzazione. Tuttavia, l'applicazione pratica di una tecnica di costruzione del testo di inizializzazione è limitata. Il testo di inizializzazione viene considerato come una singola stringa di testo; pertanto, aggiunge solo funzionalità per l'inizializzazione di un singolo parametro, a meno che non venga definito un convertitore di tipi per il comportamento di costruzione in grado di analizzare gli elementi di informazioni personalizzate e i delimitatori personalizzati dalla stringa. Inoltre, la stringa di testo per la logica dell'oggetto è potenzialmente il convertitore di tipi predefinito nativo del parser XAML per la gestione di primitive diverse da una stringa true.

L'utilizzo `x:Arguments` di XAML non è l'utilizzo dell'elemento proprietà nel senso tipico, perché il markup della direttiva non fa riferimento al tipo dell'elemento oggetto contenitore. È più simile ad altre direttive, ad `x:Code` esempio in cui l'elemento decontrassegna un intervallo in cui il markup deve essere interpretato come diverso da quello predefinito per il contenuto figlio. In questo caso, il tipo XAML di ogni elemento oggetto comunica informazioni sui tipi di argomento, utilizzati dai parser XAML per determinare a quale firma del metodo factory del costruttore specifico un `x:Arguments` utilizzo sta tentando di fare riferimento.

`x:Arguments`per un elemento oggetto da costruire deve precedere qualsiasi altro elemento proprietà, contenuto, testo interno o stringhe di inizializzazione dell'elemento oggetto. Gli elementi `x:Arguments` dell'oggetto all'interno possono includere attributi e stringhe di inizializzazione, come consentito da tale tipo XAML e dal relativo costruttore o metodo factory di supporto. Per l'oggetto o gli argomenti, è possibile specificare tipi XAML personalizzati o tipi XAML che non rientrano nello spazio dei nomi XAML predefinito facendo riferimento ai mapping dei prefissi stabiliti.

I processori XAML usano le linee guida `x:Arguments` seguenti per determinare come devono essere usati gli argomenti specificati in per costruire un oggetto. Se `x:FactoryMethod` viene specificato, le informazioni `x:FactoryMethod` vengono confrontate `x:FactoryMethod` con l'oggetto specificato (si noti che il valore di è il nome del metodo e il metodo denominato può avere overload. Se `x:FactoryMethod` non viene specificato, le informazioni vengono confrontate con il set di tutti gli overload del costruttore pubblico dell'oggetto. La logica di elaborazione XAML confronta quindi il numero di parametri e seleziona l'overload con arity corrispondente. Se è presente più di una corrispondenza, il processore XAML deve confrontare i tipi dei parametri in base ai tipi XAML degli elementi oggetto forniti. Se è ancora presente più di una corrispondenza, il comportamento del processore XAML non è definito. Se `x:FactoryMethod` viene specificato un oggetto ma il metodo non può essere risolto, un processore XAML deve generare un'eccezione.

L'utilizzo `<x:Arguments>string</x:Arguments>` di un attributo XAML è tecnicamente possibile. Tuttavia, questo non fornisce funzionalità oltre a quanto potrebbe essere fatto altrimenti attraverso il testo di inizializzazione e convertitori di tipi, e l'utilizzo di questa sintassi non è l'intenzione di progettazione delle funzionalità del metodo factory di XAML 2009.

## <a name="examples"></a>Esempi

Nell'esempio seguente viene illustrata una firma del `x:Arguments` costruttore senza parametri, quindi l'utilizzo XAML di tale accede a tale firma.

```csharp
public class Food {
  private string _name;
  private Int32 _calories;
  public Food(string name, Int32 calories) {
      _name=name;
      _calories=calories;
  }
}
```

```xaml
<my:Food>
  <x:Arguments>
      <x:String>Apple</x:String>
      <x:Int32>150</x:Int32>
  </x:Arguments>
</my:Food>
```

Nell'esempio seguente viene illustrata una firma `x:Arguments` del metodo factory di destinazione, quindi l'utilizzo XAML di tale accede a tale firma.

```csharp
public Food TryLookupFood(string name)
{
switch (name) {
  case "Apple": return new Food("Apple",150);
  case "Chocolate": return new Food("Chocolate",200);
  case "Cheese": return new Food("Cheese", 450);
  default: {return new Food(name,0);
}
}
```

```xaml
<my:Food x:FactoryMethod="TryLookupFood">
  <x:Arguments>
      <x:String>Apple</x:String>
  </x:Arguments>
</my:Food>
```

## <a name="see-also"></a>Vedere anche

- [Definizione di tipi personalizzati da usare con i servizi XAML .NET](define-custom-types.md)
- [Panoramica di XAML (WPF)](../fundamentals/xaml.md)
