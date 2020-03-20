---
title: Modelli di costruttore sicuri per DependencyObject
ms.date: 03/30/2017
helpviewer_keywords:
- constructor patterns for dependency objects [WPF]
- dependency objects [WPF], constructor patterns
- FXCop tool [WPF]
ms.assetid: f704b81c-449a-47a4-ace1-9332e3cc6d60
ms.openlocfilehash: 6d6ff444b99ca893e687731c56a48ea3ac072dd0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187228"
---
# <a name="safe-constructor-patterns-for-dependencyobjects"></a>Modelli di costruttore sicuri per DependencyObject
In genere, i costruttori di classe non devono chiamare callback come metodi virtuali o delegati, in quanto possono essere chiamati come inizializzazione di base di costruttori per una classe derivata. L'uso di elementi virtuali può avvenire in un stato incompleto dell'inizializzazione di qualsiasi dato oggetto. Il sistema di proprietà stesso, tuttavia, chiama ed espone internamente i callback come parte del sistema di proprietà di dipendenza. Semplice un'operazione come l'impostazione <xref:System.Windows.DependencyObject.SetValue%2A> di un valore della proprietà di dipendenza con chiamata include potenzialmente un callback da qualche parte nella determinazione. Per questa ragione, occorre prestare attenzione quando si impostano i valori delle proprietà di dipendenza all'interno del corpo di un costruttore, perché l'operazione può divenire problematica se il tipo viene usato come classe di base. Esiste un modello particolare <xref:System.Windows.DependencyObject> per l'implementazione di costruttori che evita problemi specifici con gli stati delle proprietà di dipendenza e i callback intrinseci, documentati qui.  

<a name="Property_System_Virtual_Methods"></a>
## <a name="property-system-virtual-methods"></a>Metodi virtuali del sistema di proprietà  
 I seguenti metodi virtuali o callback vengono potenzialmente <xref:System.Windows.DependencyObject.SetValue%2A> chiamati durante i calcoli della <xref:System.Windows.ValidateValueCallback> <xref:System.Windows.PropertyChangedCallback>chiamata <xref:System.Windows.CoerceValueCallback> <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>che imposta un valore della proprietà di dipendenza: , , , . Ognuno di questi metodi virtuali o callback serve a uno scopo particolare nell'espansione della versatilità del sistema di proprietà [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] e delle proprietà di dipendenza. Per altre informazioni su come usare questi elementi virtuali per personalizzare la determinazione del valore della proprietà, vedere [Callback e convalida delle proprietà di dipendenza](dependency-property-callbacks-and-validation.md).  
  
### <a name="fxcop-rule-enforcement-vs-property-system-virtuals"></a>Applicazione delle regole FXCop rispetto alle impostazioni virtuali del sistema di proprietà  
 Se si usa lo strumento Microsoft FXCop come parte del processo di compilazione e si esegue la derivazione da determinate classi del framework [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che chiamano il costruttore di base oppure si implementano proprietà di dipendenza personalizzate sulle classi derivate, può verificarsi la violazione di una particolare regola FXCop. La stringa del nome di questa violazione è:  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 Si tratta di una regola che fa parte del set di regole pubblico predefinito per FXCop. È possibile che questa regola segnali una traccia tramite il sistema di proprietà di dipendenza che infine chiama il metodo virtuale di un sistema di proprietà di dipendenza. La violazione di questa regola potrebbe continuare ad apparire anche dopo avere seguito i modelli del costruttore consigliati illustrati in questo argomento, pertanto potrebbe essere necessario disabilitare o eliminare la regola nella configurazione del set di regole FXCop.  
  
### <a name="most-issues-come-from-deriving-classes-not-using-existing-classes"></a>La maggior parte dei problemi è causata dalla derivazione delle classi e dal mancato uso delle classi esistenti  
 I problemi segnalati da questa regola si verificano quando una classe implementata con metodi virtuali nella relativa sequenza di costruzione viene successivamente derivata. Se la classe viene contrassegnata come sealed oppure si sa o si decide che la classe non sarà derivata, le considerazioni qui illustrate e i problemi che hanno motivato la regola FXCop non si applicano a questa situazione. Se tuttavia se si stanno creando classi in modo che vengano usate come classi di base, ad esempio se si stanno creando modelli o un set di librerie di controlli espandibile, è consigliabile seguire i modelli raccomandati in questo argomento per i costruttori.  
  
### <a name="default-constructors-must-initialize-all-values-requested-by-callbacks"></a>I costruttori predefiniti devono inizializzare tutti i valori richiesti dai callback  
 Tutti i membri di istanza utilizzati dagli override o dai callback della classe (i callback dall'elenco nella sezione Virtuals del sistema di proprietà) devono essere inizializzati nel costruttore senza parametri della classe, anche se alcuni di questi valori sono riempiti da valori "reali" tramite parametri dei costruttori senza parametri.  
  
 L'esempio di codice seguente e i successivi sono esempi di pseudo codice C# in cui questa regola viene violata e in cui viene illustrato il problema:  
  
```csharp  
public class MyClass : DependencyObject  
{  
    public MyClass() {}  
    public MyClass(object toSetWobble)  
        : this()  
    {  
        Wobble = toSetWobble; //this is backed by a DependencyProperty  
        _myList = new ArrayList();    // this line should be in the default ctor  
    }  
    public static readonly DependencyProperty WobbleProperty =
        DependencyProperty.Register("Wobble", typeof(object), typeof(MyClass));  
    public object Wobble  
    {  
        get { return GetValue(WobbleProperty); }  
        set { SetValue(WobbleProperty, value); }  
    }  
    protected override void OnPropertyChanged(DependencyPropertyChangedEventArgs e)  
    {  
        int count = _myList.Count;    // null-reference exception  
    }  
    private ArrayList _myList;  
}  
```  
  
 Quando il `new MyClass(objectvalue)`codice dell'applicazione chiama , chiama il costruttore senza parametri e i costruttori della classe base. Quindi imposta `Property1 = object1`, che chiama `OnPropertyChanged` il metodo `MyClass` <xref:System.Windows.DependencyObject>virtuale sulla proprietà di .  L'override fa riferimento a `_myList`, che non è stato ancora inizializzato.  
  
 Un modo per evitare questi problemi consiste nel verificare che i callback usino solo altre proprietà di dipendenza e che ognuna di esse abbia un valore predefinito stabilito come parte dei relativi metadati registrati.  
  
<a name="Safe_Constructor_Patterns"></a>
## <a name="safe-constructor-patterns"></a>Modelli di costruttore sicuri  
 Per evitare i rischi di un'inizializzazione incompleta nel caso in cui la classe sia usata come classe di base, seguire questi modelli:  
  
#### <a name="parameterless-constructors-calling-base-initialization"></a>Costruttori senza parametri che chiamano l'inizializzazione di baseParameterless constructors calling base initialization  
 Implementare questi costruttori che chiamano l'impostazione predefinita di base:  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-not-matching-any-base-signatures"></a>Costruttori non predefiniti (di comodo), che non corrispondono ad alcuna firma di base  
 Se questi costruttori utilizzano i parametri per impostare le proprietà di dipendenza nell'inizializzazione, chiamare prima il proprio costruttore senza parametri della classe per l'inizializzazione, quindi utilizzare i parametri per impostare le proprietà di dipendenza. Queste ultime potrebbero essere proprietà di dipendenza definite dalla classe o proprietà di dipendenza ereditate dalle classi di base. In entrambi i casi, tuttavia, usare il modello seguente:  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-which-do-match-base-signatures"></a>Costruttori non predefiniti (di comodo), che corrispondono alle firme di base  
 Invece di chiamare il costruttore di base con la stessa parametrizzazione, chiamare nuovamente il costruttore senza parametri della propria classe. Non chiamare l'inizializzatore di base, bensì chiamare `this()`. A questo punto, riprodurre il comportamento del costruttore originale usando i parametri passati come valori per l'impostazione delle proprietà pertinenti. Per informazioni sulla determinazione delle proprietà da impostare tramite determinati parametri, usare la documentazione originale del costruttore di base:  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="must-match-all-signatures"></a>Deve corrispondere a tutte le firme  
 Per i casi in cui il tipo di base ha più firme, è necessario associare deliberatamente tutte le firme possibili con un'implementazione del costruttore personalizzata che utilizza il modello consigliato di chiamare il costruttore senza parametri della classe prima di impostare ulteriori Proprietà.  
  
#### <a name="setting-dependency-properties-with-setvalue"></a>Impostazione delle proprietà di dipendenza con SetValue  
 Questi stessi modelli si applicano se si imposta una proprietà che non <xref:System.Windows.DependencyObject.SetValue%2A>dispone di un wrapper per la praticità dell'impostazione della proprietà e si impostano i valori con . Le chiamate <xref:System.Windows.DependencyObject.SetValue%2A> a che passano attraverso i parametri del costruttore devono anche chiamare il costruttore senza parametri della classe per l'inizializzazione.  
  
## <a name="see-also"></a>Vedere anche

- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
- [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Sicurezza della proprietà di dipendenza](dependency-property-security.md)
