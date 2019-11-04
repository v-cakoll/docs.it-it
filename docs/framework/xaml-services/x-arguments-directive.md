---
title: Direttiva x:Arguments
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 338286b417c78b7cceeb30188e888928a15607cd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458649"
---
# <a name="xarguments-directive"></a>Direttiva x:Arguments
Pacchetti gli argomenti di costruzione per una dichiarazione di elemento oggetto costruttore senza parametri in XAML o per una dichiarazione di oggetto Metodo Factory.  
  
## <a name="xaml-element-usage-nonparameterless-constructor"></a>Utilizzo di elementi XAML (costruttore senza parametri)  
  
```xaml  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a>Utilizzo di elementi XAML (metodo Factory)  
  
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
|`oneOrMoreObjectElements`|Uno o più elementi oggetto che specificano gli argomenti da passare al costruttore o al metodo factory sottostante senza parametri.<br /><br /> L'utilizzo tipico consiste nell'utilizzare il testo di inizializzazione negli elementi oggetto per specificare i valori effettivi degli argomenti. Vedere la sezione esempi.<br /><br /> L'ordine degli elementi è significativo. I tipi XAML in ordine devono corrispondere ai tipi e all'ordine del tipo del costruttore di supporto o dell'overload del metodo factory.|  
|`methodName`|Nome del metodo factory che deve elaborare eventuali argomenti di `x:Arguments`.|  
  
## <a name="dependencies"></a>Dipendenze  
 `x:FactoryMethod` possibile modificare l'ambito e il comportamento in cui si applica `x:Arguments`.  
  
 Se non viene specificato alcun `x:FactoryMethod`, `x:Arguments` si applica alle firme alternative (non predefinite) dei costruttori di supporto.  
  
 Se viene specificato `x:FactoryMethod`, `x:Arguments` si applica a un overload del metodo denominato.  
  
## <a name="remarks"></a>Note  
 XAML 2006 può supportare l'inizializzazione non predefinita tramite il testo di inizializzazione. Tuttavia, l'applicazione pratica di una tecnica di costruzione del testo di inizializzazione è limitata. Il testo di inizializzazione viene considerato come una singola stringa di testo; viene pertanto aggiunta solo la funzionalità per l'inizializzazione di un singolo parametro, a meno che non venga definito un convertitore di tipi per il comportamento di costruzione che può analizzare elementi di informazioni personalizzate e delimitatori personalizzati dalla stringa. Inoltre, la stringa di testo alla logica dell'oggetto è potenzialmente un convertitore di tipi predefinito nativo del parser XAML per la gestione di primitive diverse da una stringa vera.  
  
 Il `x:Arguments` utilizzo di XAML non è l'utilizzo dell'elemento proprietà nel senso tipico, perché il markup della direttiva non fa riferimento al tipo dell'elemento oggetto contenitore. È più simile ad altre direttive, ad esempio `x:Code` in cui l'elemento contrassegna un intervallo in cui il markup deve essere interpretato come diverso da quello predefinito per il contenuto figlio. In questo caso, il tipo XAML di ogni elemento oggetto comunica informazioni sui tipi di argomento utilizzati dai parser XAML per determinare quale firma del metodo factory del costruttore specifico un utilizzo `x:Arguments` sta tentando di fare riferimento a.  
  
 `x:Arguments` per un elemento oggetto da costruire devono precedere qualsiasi altro elemento di proprietà, contenuto, testo interno o stringhe di inizializzazione dell'elemento oggetto. Gli elementi dell'oggetto all'interno di `x:Arguments` possono includere attributi e stringhe di inizializzazione, come consentito dal tipo XAML e dal costruttore di supporto o dal metodo factory. Per l'oggetto o per gli argomenti, è possibile specificare tipi XAML personalizzati o tipi XAML che non rientrano nello spazio dei nomi XAML predefinito facendo riferimento ai mapping di prefisso stabiliti.  
  
 I processori XAML usano le linee guida seguenti per determinare il modo in cui gli argomenti specificati in `x:Arguments` devono essere usati per costruire un oggetto. Se viene specificato `x:FactoryMethod`, le informazioni vengono confrontate con il `x:FactoryMethod` specificato (si noti che il valore di `x:FactoryMethod` è il nome del metodo e il metodo denominato può avere overload. Se `x:FactoryMethod` viene omesso, le informazioni vengono confrontate con il set di tutti gli overload del costruttore pubblico dell'oggetto. La logica di elaborazione XAML confronta quindi il numero di parametri e seleziona l'overload con grado corrispondente. Se è presente più di una corrispondenza, il processore XAML deve confrontare i tipi di parametri in base ai tipi XAML degli elementi oggetto forniti. Se è ancora presente più di una corrispondenza, il comportamento del processore XAML non è definito. Se viene specificato un `x:FactoryMethod` ma il metodo non può essere risolto, un processore XAML deve generare un'eccezione.  
  
 Un `<x:Arguments>string</x:Arguments>` di utilizzo degli attributi XAML è tecnicamente possibile. Tuttavia, non fornisce alcuna funzionalità oltre a quelle che potrebbero essere eseguite in altro modo tramite il testo di inizializzazione e i convertitori di tipi e l'utilizzo di questa sintassi non è l'intenzione di progettazione delle funzionalità del metodo factory XAML 2009.  
  
## <a name="examples"></a>Esempi  
 Nell'esempio seguente viene illustrata una firma del costruttore senza parametri, quindi l'utilizzo di XAML di `x:Arguments` che accede a tale firma.  
  
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
  
 Nell'esempio seguente viene illustrata la firma di un metodo factory di destinazione, quindi l'utilizzo XAML di `x:Arguments` che accede a tale firma.  
  
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

- [Definizione di tipi personalizzati da utilizzare con i servizi XAML di .NET Framework](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [Cenni preliminari su XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
