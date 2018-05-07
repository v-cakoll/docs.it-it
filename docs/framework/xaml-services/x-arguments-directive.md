---
title: Direttiva x:Arguments
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: e0e7f380ec176e80d2422878a2e676d64985d660
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="xarguments-directive"></a>Direttiva x:Arguments
Argomenti di costruzione di pacchetti per una dichiarazione di elemento oggetto costruttore non predefinito in XAML o per una dichiarazione di oggetto del metodo factory.  
  
## <a name="xaml-element-usage-nondefault-constructor"></a>Utilizzo dell'elemento XAML (costruttore non predefinito)  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a>Utilizzo dell'elemento XAML (metodo factory)  
  
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
|`oneOrMoreObjectElements`|Uno o più elementi di oggetti che specificano gli argomenti da passare per il backup non predefinito costruttore o metodo factory.<br /><br /> Utilizzo tipico consiste nell'utilizzare il testo di inizializzazione all'interno gli elementi oggetto per specificare i valori di argomento effettivo. Vedere la sezione esempi.<br /><br /> L'ordine degli elementi è significativo. I tipi XAML in ordine necessario corrispondono ai tipi e digitare ordine backup costruttore o overload del metodo.|  
|`methodName`|Il nome del metodo factory che deve elaborare tutti `x:Arguments` argomenti.|  
  
## <a name="dependencies"></a>Dipendenze  
 `x:FactoryMethod` può modificare l'ambito e il comportamento in `x:Arguments` si applica.  
  
 Se non `x:FactoryMethod` è specificato, `x:Arguments` si applica a alternative (non-impostazione predefinita) firme dei costruttori di backup.  
  
 Se `x:FactoryMethod` è specificato, `x:Arguments` si applica a un overload del metodo denominato.  
  
## <a name="remarks"></a>Note  
 XAML 2006 supporta l'inizializzazione non predefinita, tramite il testo di inizializzazione. Tuttavia, l'applicazione di una tecnica di costruzione di testo di inizializzazione è limitato. Testo di inizializzazione viene considerato come una stringa di testo singola. Pertanto, solo aggiunge funzionalità per l'inizializzazione di un singolo parametro a meno che non è definito un convertitore di tipi per il comportamento di costruzione che consente di analizzare gli elementi di informazioni personalizzate e delimitatori personalizzati dalla stringa. Inoltre, la stringa di testo alla logica dell'oggetto è potenzialmente convertitore di tipi predefiniti nativo del parser XAML specificato per le primitive diverso da una stringa true.  
  
 Il `x:Arguments` utilizzo di XAML non è utilizzo dell'elemento proprietà in senso tradizionale, perché il markup della direttiva non fa riferimento il tipo dell'elemento oggetto contenitore. È più simile alle altre direttive, ad esempio `x:Code` in cui l'elemento delimita un intervallo in cui il markup deve essere interpretato come diverso da quello predefinito per il contenuto figlio. In questo caso, il tipo XAML di ogni elemento oggetto comunica informazioni relative ai tipi di argomenti, che viene usate dal parser XAML per determinare quali firma del metodo factory costruttore specifico un `x:Arguments` utilizzo sta tentando di fare riferimento.  
  
 `x:Arguments` per un elemento oggetto in fase di costruzione devono precedere eventuali altri elementi di proprietà, contenuto, testo interno o stringhe di inizializzazione dell'elemento oggetto. Gli elementi oggetto all'interno di `x:Arguments` possono includere attributi e stringhe di inizializzazione, come consentito dal tipo XAML e il relativo metodo di costruttore o di backup. Per l'oggetto o gli argomenti, è possibile specificare tipi XAML personalizzati o tipi XAML che non rientrano in caso contrario lo spazio dei nomi XAML predefinito facendo riferimento a mapping del prefisso stabilita.  
  
 Processori XAML utilizzano le linee guida seguenti per determinare la modalità con cui gli argomenti specificati nella `x:Arguments` deve essere utilizzato per costruire un oggetto. Se `x:FactoryMethod` è specificato, le informazioni vengono confrontate specificata `x:FactoryMethod` (si noti che il valore di `x:FactoryMethod` è il nome del metodo e il metodo denominato può disporre di overload. Se `x:FactoryMethod` non viene specificato, le informazioni vengono confrontate al set di tutti gli overload di costruttore pubblico dell'oggetto. Logica di elaborazione XAML quindi confronta il numero di parametri e seleziona l'overload con grado corrispondente. Se è presente più di una corrispondenza, il processore XAML deve confrontare i tipi dei parametri in base ai tipi di sintassi XAML per gli elementi oggetto fornito. Se è ancora più corrispondenze, non è definito il comportamento del processore XAML. Se un `x:FactoryMethod` è specificato, ma il metodo non può essere risolto, un processore XAML deve generare un'eccezione.  
  
 Attributo XAML `<x:Arguments>string</x:Arguments>` è tecnicamente possibile. Tuttavia, ciò non fornisce alcuna funzionalità oltre a ciò che potrebbe avvenire in caso contrario tramite i convertitori di tipi e di testo di inizializzazione e utilizzando questa sintassi, non è l'intenzione di progettazione delle funzionalità di metodo factory di XAML 2009.  
  
## <a name="examples"></a>Esempi  
 L'esempio seguente mostra un costruttore non predefinito, firma, quindi l'utilizzo di XAML `x:Arguments` che accede alla firma.  
  
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
  
 L'esempio seguente mostra una firma del metodo factory di destinazione, quindi l'utilizzo di XAML `x:Arguments` che accede alla firma.  
  
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
 [Definizione di tipi personalizzati da utilizzare con i servizi XAML di .NET Framework](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)  
 [Cenni preliminari su XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
