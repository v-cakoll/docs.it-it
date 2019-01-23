---
title: Direttiva x:Arguments
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: d4cff4c2f95d1418371921a3ac992a3b243d1c07
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490817"
---
# <a name="xarguments-directive"></a>Direttiva x:Arguments
Argomenti di costruzione di pacchetti per una dichiarazione dell'elemento oggetto costruttore non predefinito in XAML o per una dichiarazione dell'oggetto metodo factory.  
  
## <a name="xaml-element-usage-nondefault-constructor"></a>Utilizzo di un elemento XAML (costruttore non predefinito)  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a>Utilizzo di un elemento XAML (metodo factory)  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|Uno o più elementi di oggetti che specificano gli argomenti da passare per il metodo factory o costruttore non predefinito sottostante.<br /><br /> Utilizzo tipico consiste nell'usare il testo di inizializzazione all'interno di elementi oggetto per specificare i valori di argomento effettivo. Vedere la sezione esempi.<br /><br /> L'ordine degli elementi è significativo. I tipi XAML in ordine necessario corrispondono ai tipi e digitare ordine sottostante factory o costruttore di overload del metodo.|  
|`methodName`|Il nome del metodo factory che deve elaborare qualsiasi `x:Arguments` argomenti.|  
  
## <a name="dependencies"></a>Dipendenze  
 `x:FactoryMethod` può modificare l'ambito e il comportamento in cui `x:Arguments` si applica.  
  
 Se nessun `x:FactoryMethod` viene specificato, `x:Arguments` si applica a alternative (diverso) delle firme dei costruttori di backup.  
  
 Se `x:FactoryMethod` viene specificato, `x:Arguments` si applica a un overload del metodo denominato.  
  
## <a name="remarks"></a>Note  
 XAML 2006 possono supportare l'inizializzazione non predefinito tramite il testo di inizializzazione. Tuttavia, l'applicazione pratica di una tecnica di costruzione di testo di inizializzazione è limitato. Testo di inizializzazione viene considerato come una singola stringa di testo; Pertanto, solo aggiunge funzionalità per l'inizializzazione di un singolo parametro che non sia definito un convertitore di tipi per il comportamento di costruzione che consente di analizzare gli elementi di informazioni personalizzate e i delimitatori personalizzati dalla stringa. Inoltre, la stringa di testo alla logica dell'oggetto è potenzialmente convertitore di tipi predefiniti nativi del parser XAML specificato per le primitive diverso da una stringa true.  
  
 Il `x:Arguments` sull'utilizzo XAML non utilizzo dell'elemento di proprietà nel senso tradizionale, perché il markup della direttiva non fa riferimento il tipo dell'elemento oggetto che lo contiene. È più simile a altre direttive, ad esempio `x:Code` dove l'elemento delimita un intervallo in cui il markup deve essere interpretato come diversa da quella predefinita per il contenuto figlio. In questo caso, il tipo XAML di ogni elemento oggetto comunica informazioni sui tipi di argomento, che viene usate dal parser XAML per determinare quali firma del metodo factory costruttore specifico un `x:Arguments` utilizzo sta provando a fare riferimento.  
  
 `x:Arguments` per un elemento dell'oggetto in fase di costruzione devono precedere eventuali altri elementi proprietà, contenuto, il testo interno o stringhe di inizializzazione dell'elemento oggetto. Gli elementi oggetto all'interno di `x:Arguments` possono includere attributi e le stringhe di inizializzazione, come consentito dal tipo XAML e il relativo metodo di costruttore o factory sottostante. Per l'oggetto o gli argomenti, è possibile specificare tipi XAML personalizzati o XAML che non rientrano in caso contrario, lo spazio dei nomi XAML predefinito facendo riferimento a mapping del prefisso stabiliti.  
  
 Processori XAML usano le linee guida seguenti per determinare come gli argomenti specificati nel `x:Arguments` deve essere utilizzato per costruire un oggetto. Se `x:FactoryMethod` viene specificato, viene confrontata con le informazioni sull'oggetto specificato `x:FactoryMethod` (si noti che il valore di `x:FactoryMethod` è il nome del metodo e il metodo denominato può avere gli overload. Se `x:FactoryMethod` non viene specificato, le informazioni viene confrontato con il set di tutti gli overload di un costruttore pubblico dell'oggetto. Logica di elaborazione XAML quindi confronta il numero di parametri e seleziona l'overload con il grado corrispondente. Se è presente più di una corrispondenza, il processore XAML deve confrontare i tipi dei parametri in base ai tipi XAML degli elementi oggetto specificati. Se non esiste ancora più di una corrispondenza, il comportamento del processore XAML è definito. Se un `x:FactoryMethod` è specificato, ma il metodo non può essere risolto, un processore XAML deve generare un'eccezione.  
  
 Un utilizzo dell'attributo XAML `<x:Arguments>string</x:Arguments>` sia tecnicamente possibile. Tuttavia, ciò non fornisce alcuna funzionalità oltre a ciò che avveniva in caso contrario, tramite i convertitori di tipi e il testo di inizializzazione e usando questa sintassi non è l'intenzione di progettazione di funzionalità del metodo factory di XAML 2009.  
  
## <a name="examples"></a>Esempi  
 Nell'esempio seguente illustra un costruttore non predefinito, firma, quindi l'utilizzo XAML di `x:Arguments` che accede alla firma.  
  
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
  
 L'esempio seguente mostra una firma di metodo factory di destinazione, quindi l'utilizzo XAML di `x:Arguments` che accede alla firma.  
  
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
- [Definizione di tipi personalizzati da utilizzare con i servizi XAML di .NET Framework](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [Cenni preliminari su XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
