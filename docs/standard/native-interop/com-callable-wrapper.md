---
title: COM Callable Wrapper
ms.date: 10/23/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CCW
- COM interop, COM wrappers
- COM wrappers
- callable wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: d04be3b5-27b9-4f5b-8469-a44149fabf78
ms.openlocfilehash: 6f2f4055a95dbcea8d7872b5c5fa3ccede8c2c8c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400379"
---
# <a name="com-callable-wrapper"></a>COM Callable Wrapper

Quando un client COM chiama un oggetto .NET, Common Language Runtime crea l'oggetto gestito e un COM Callable Wrapper (CCW) per l'oggetto. Incapaci di fare riferimento diretto a un oggetto .NET, i client COM usano il CCW come un proxy per l'oggetto gestito.

Il runtime crea esattamente un CCW per ciascun oggetto gestito, indipendentemente dal numero di client COM che ne richiedono i servizi. Come mostrato nella figura seguente, più client COM possono mantenere un riferimento allo stesso CCW che espone l'interfaccia INew. Il CCW mantiene a sua volta un solo riferimento all'oggetto gestito che implementa l'interfaccia ed è sottoposto alla procedura di Garbage Collection. Sia i client COM che i client .NET possono effettuare contemporaneamente richieste sullo stesso oggetto gestito.

![Più client COM contenenti un riferimento al CCW che espone INew.](./media/com-callable-wrapper/com-callable-wrapper-clients.gif)

Gli oggetti COM Callable Wrapper sono invisibili alle altre classi in esecuzione nel runtime .NET Framework. Il loro scopo principale è effettuare il marshalling delle chiamate tra il codice gestito e quello non gestito. Tuttavia, i CCW gestiscono anche l'identità e la durata degli oggetti gestiti di cui eseguono il wrapping.

## <a name="object-identity"></a>Identità dell'oggetto

Il runtime alloca per l'oggetto .NET memoria attinta dall'heap sottoposto a Garbage Collection. In tal modo si consente al runtime di spostare l'oggetto in memoria a seconda delle esigenze. Al contrario, il runtime alloca per il CCW memoria attinta da un heap non soggetto a Garbage Collection, consentendo così ai client COM di fare riferimento al wrapper direttamente.

## <a name="object-lifetime"></a>Durata dell'oggetto

Diversamente dal client .NET di cui esegue il wrapping, il CCW è destinatario di riferimenti conteggiati in modo tradizionale (COM). Quando il conteggio dei riferimenti al CCW raggiunge lo zero, il wrapper rilascia il proprio riferimento all'oggetto gestito. Gli oggetti gestiti senza più riferimenti vengono raccolti durante la successiva procedura di Garbage Collection.

## <a name="simulating-com-interfaces"></a>Simulazione di interfacce COM

CCW espone ai client COM tutti i tipi di dati, i valori restituiti e le interfacce pubbliche visibili a COM in modo conforme al meccanismo di interazione COM basato sulle interfacce. Per un client COM, richiamare i metodi in un oggetto .NET equivale a richiamarli in un oggetto COM.

Per assicurare questo approccio naturale, il CCW crea interfacce COM tradizionali quali **IUnknown** e **IDispatch**. Come mostrato nella figura seguente, il CCW mantiene un solo riferimento all'oggetto .NET di cui esegue il wrapping. Il client COM e l'oggetto .NET interagiscono tramite il proxy e lo stub del CCW.

![Diagramma che mostra come CCW crea interfacce COM.](./media/com-callable-wrapper/com-callable-wrapper-interfaces.gif)

Oltre a esporre le interfacce che sono esplicitamente implementate da una classe dell'ambiente gestito, il runtime .NET fornisce le implementazioni delle interfacce COM elencate nella tabella seguente per conto dell'oggetto. Una classe .NET può eseguire l'override del comportamento predefinito fornendo la propria implementazione di queste interfacce. Il runtime, tuttavia, fornisce sempre l'implementazione delle interfacce **IUnknown** e **IDispatch**.

|Interfaccia|Descrizione|
|---------------|-----------------|
|**Idispatch**|Fornisce un meccanismo per l'associazione tardiva al tipo.|
|**IErrorInfo**|Fornisce una descrizione testuale dell'errore, la relativa origine, un file della Guida, un contesto della Guida e il GUID dell'interfaccia che ha definito l'errore (sempre **GUID_NULL** per le classi .NET).|
|**IProvideClassInfo**|Consente ai client COM di ottenere l'accesso all'interfaccia **ITypeInfo** implementata da una classe gestita. Restituisce `COR_E_NOTSUPPORTED` in .NET Core per i tipi non importati da COM. |
|**ISupportErrorInfo**|Consente a un client COM di determinare se l'oggetto gestito supporta l'interfaccia **IErrorInfo**. Se sì, consente al client di ottenere un puntatore all'ultimo oggetto eccezione. Tutti i tipi gestiti supportano l'interfaccia **IErrorInfo**.|
|**ITypeInfo** (solo .NET Framework)|Fornisce per le classi le stesse informazioni sul tipo che fornisce Tlbexp.exe.|
|**Iunknown**|Fornisce l'implementazione standard dell'interfaccia **IUnknown** con cui il client COM gestisce la durata del CCW e provvede alla coercizione dei tipi.|

 Le classi gestite possono anche fornire le interfacce COM descritte nella tabella che segue.

|Interfaccia|Descrizione|
|---------------|-----------------|
|Interfaccia\_di classe (*classname*)|Interfaccia, esposta dal runtime e non definita esplicitamente, che espone tutte le interfacce, i metodi, le proprietà e i campi pubblici esplicitamente esposti su un oggetto gestito.|
|**IConnectionPoint** e **IConnectionPointContainer**|Interfaccia per oggetti che originano eventi basati su delegati (un'interfaccia per la registrazione di sottoscrittori di eventi).|
|**IDispatchEx** (solo .NET Framework)|Interfaccia fornita dal runtime se la classe implementa **IExpando**. L'interfaccia **IDispatchEx** è un'estensione dell'interfaccia **IDispatch** che, diversamente da **IDispatch**, consente l'enumerazione, l'aggiunta, l'eliminazione e la chiamata dei membri con distinzione tra maiuscole e minuscole.|
|**IEnumVARIANT**|Interfaccia per classi Collection che enumera gli oggetti della raccolta se la classe implementa **IEnumerable**.|

## <a name="introducing-the-class-interface"></a>Introduzione all'interfaccia della classe

L'interfaccia della classe, che non è definita esplicitamente nel codice gestito, è un'interfaccia che espone tutte le proprietà, i campi, gli eventi e i metodi pubblici esplicitamente esposti dall'oggetto .NET. Tale interfaccia può essere duale o solo dispatch. L'interfaccia della classe riceve il nome dalla classe .NET stessa, preceduto da un carattere di sottolineatura. Per la classe Mammal, ad esempio, l'interfaccia della classe sarà \_Mammal.

Per le classi derivate, l'interfaccia della classe espone anche tutti i metodi, le proprietà e i campi pubblici della classe base. La classe derivata espone anche un'interfaccia della classe per ciascuna classe base. Ad esempio, se la classe Mammal estende la classe MammalSuperclass, che a sua volta estende la classe System.Object, l'oggetto .NET espone ai client COM tre interfacce della classe denominate \_Mammal, \_MammalSuperclass e \_Object.

Si consideri ad esempio la classe .NET seguente:

```vb
' Applies the ClassInterfaceAttribute to set the interface to dual.
<ClassInterface(ClassInterfaceType.AutoDual)> _
' Implicitly extends System.Object.
Public Class Mammal
    Sub Eat()
    Sub Breathe()
    Sub Sleep()
End Class
```

```csharp
// Applies the ClassInterfaceAttribute to set the interface to dual.
[ClassInterface(ClassInterfaceType.AutoDual)]
// Implicitly extends System.Object.
public class Mammal
{
    public void Eat() {}
    public void Breathe() {}
    public void Sleep() {}
}
```

Il client COM può ottenere un puntatore a un'interfaccia di classe denominata `_Mammal`. In .NET Framework è possibile usare l'[utilità di esportazione della libreria dei tipi (Tlbexp.exe)](../../framework/tools/tlbexp-exe-type-library-exporter.md) per generare una libreria dei tipi contenente la definizione dell'interfaccia `_Mammal`. L'utilità di esportazione della libreria dei tipi non è supportata in .NET Core. Se la classe `Mammal` implementa una o più interfacce, queste appariranno sotto la coclasse.

```console
[odl, uuid(…), hidden, dual, nonextensible, oleautomation]
interface _Mammal : IDispatch
{
    [id(0x00000000), propget] HRESULT ToString([out, retval] BSTR*
        pRetVal);
    [id(0x60020001)] HRESULT Equals([in] VARIANT obj, [out, retval]
        VARIANT_BOOL* pRetVal);
    [id(0x60020002)] HRESULT GetHashCode([out, retval] short* pRetVal);
    [id(0x60020003)] HRESULT GetType([out, retval] _Type** pRetVal);
    [id(0x6002000d)] HRESULT Eat();
    [id(0x6002000e)] HRESULT Breathe();
    [id(0x6002000f)] HRESULT Sleep();
}
[uuid(…)]
coclass Mammal
{
    [default] interface _Mammal;
}
```

La generazione dell'interfaccia della classe è facoltativa. Per impostazione predefinita, l'interoperabilità COM genera un'interfaccia solo dispatch per ogni classe esportata in una libreria dei tipi. È possibile modificare o impedire la creazione automatica di questa interfaccia applicando alla classe l'oggetto <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>. Benché l'interfaccia della classe possa semplificare l'esposizione di classi gestite a COM, gli usi che è possibile farne sono limitati.

> [!CAUTION]
> Usare l'interfaccia della classe, anziché definire esplicitamente un'interfaccia personalizzata, può complicare il futuro controllo delle versioni della classe gestita. Prima di usare l'interfaccia della classe, leggere le indicazioni riportate di seguito.

### <a name="define-an-explicit-interface-for-com-clients-to-use-rather-than-generating-the-class-interface"></a>Definire un'interfaccia esplicita per i client COM anziché generare l'interfaccia della classe.

Poiché l'interoperabilità COM genera l'interfaccia della classe automaticamente, le modifiche apportate alla classe dopo l'emissione di una versione possono alterare il layout dell'interfaccia della classe esposta da Common Language Runtime. Se si cambia il layout dei membri della classe, la maggior parte dei client COM, che solitamente non è in grado di gestire le modifiche al layout di un'interfaccia, cesserà di funzionare.

Queste indicazioni ribadiscono il concetto che le interfacce esposte ai client COM devono restare immodificabili. Per ridurre il rischio di compromettere il funzionamento dei client COM riordinando inavvertitamente il layout dell'interfaccia, separare tutte le modifiche alla classe dal layout dell'interfaccia definendo esplicitamente le interfacce.

Usare **ClassInterfaceAttribute** per disattivare la generazione automatica dell'interfaccia della classe e implementare un'interfaccia esplicita per la classe, come illustrato nel frammento di codice seguente:

```vb
<ClassInterface(ClassInterfaceType.None)>Public Class LoanApp
    Implements IExplicit
    Sub M() Implements IExplicit.M
…
End Class
```

```csharp
[ClassInterface(ClassInterfaceType.None)]
public class LoanApp : IExplicit
{
    int IExplicit.M() { return 0; }
}
```

Il valore **ClassInterfaceType.None** impedisce la generazione dell'interfaccia della classe quando i metadati della classe vengono esportati in una libreria dei tipi. Nel precedente esempio, i client COM possono accedere alla classe `LoanApp` solo tramite l'interfaccia `IExplicit`.

### <a name="avoid-caching-dispatch-identifiers-dispids"></a>Evitare la memorizzazione nella cache degli identificatori dispatch (DispId)

L'uso dell'interfaccia della classe è ammissibile per i client basati su script, i client Microsoft Visual Basic 6.0 o qualsiasi client ad associazione tardiva che non inserisce nella cache i DispId dei membri di interfaccia. I DispId identificano i membri di interfaccia per abilitare l'associazione tardiva.

Per l'interfaccia della classe, la generazione dei DispId è basata sulla posizione dei membri nell'interfaccia. Se si cambia l'ordine dei membri e si esporta la classe in una libreria dei tipi, si altereranno i DispId generati nell'interfaccia della classe.

Per evitare di compromettere il funzionamento dei client COM ad associazione tardiva quando si usa questa interfaccia, applicare **ClassInterfaceAttribute** con il valore **ClassInterfaceType.AutoDispatch**. Tale valore implementa un'interfaccia della classe solo dispatch, ma omette la descrizione dell'interfaccia dalla libreria dei tipi. Senza una descrizione dell'interfaccia, i client non potranno inserire i DispId nella cache in fase di compilazione. Benché questo sia il tipo di interfaccia predefinito per l'interfaccia della classe, è possibile applicare il valore dell'attributo in modo esplicito.

```vb
<ClassInterface(ClassInterfaceType.AutoDispatch)> Public Class LoanApp
    Implements IAnother
    Sub M() Implements IAnother.M
…
End Class
```

```csharp
[ClassInterface(ClassInterfaceType.AutoDispatch)]
public class LoanApp
{
    public int M() { return 0; }
}
```

Per ottenere il DispId di un membro di interfaccia in fase di esecuzione, i client COM possono chiamare **IDispatch.GetIdsOfNames**. Per richiamare un metodo sull'interfaccia, passare il DispId restituito come argomento a **IDispatch.Invoke**.

### <a name="restrict-using-the-dual-interface-option-for-the-class-interface"></a>Limitare l'uso dell'opzione di interfaccia duale per l'interfaccia della classe.

Le interfacce duali permettono ai client COM di effettuare sia l'associazione anticipata che l'associazione tardiva ai membri di interfaccia. In fase di progettazione e durante il test, può risultare utile impostare l'interfaccia della classe su duale. Per una classe gestita (e le relative classi base) che non verrà mai modificata, questa opzione è accettabile. In tutti gli altri casi è preferibile evitare di impostare l'interfaccia della classe su duale.

Un'interfaccia duale generata automaticamente può essere appropriata in alcuni casi meno comuni. Nella maggior parte dei casi creerà invece complicazioni in relazione alla gestione delle versioni. Ad esempio, il funzionamento dei client COM che usano l'interfaccia della classe di una classe derivata verrà facilmente compromesso in conseguenza di modifiche della classe base. Quando la classe base è fornita da terzi, il layout dell'interfaccia della classe sarà fuori dal proprio controllo. Diversamente da un'interfaccia solo dispatch, un'interfaccia duale (**ClassInterfaceType.AutoDual**) fornisce anche una descrizione dell'interfaccia della classe nella libreria dei tipi esportata. Tale descrizione invita i client ad associazione tardiva a memorizzare nella cache i DispId in fase di compilazione.

### <a name="ensure-that-all-com-event-notifications-are-late-bound"></a>Verificare che tutte le notifiche degli eventi COM siano ad associazione tardiva.

Per impostazione predefinita, le informazioni sui tipi COM sono incorporate direttamente negli assembly gestiti, eliminando così la necessità di assembly di interoperabilità primari. Tuttavia, uno dei limiti delle informazioni sui tipi incorporate è dato dal fatto che non è supportato il recapito di notifiche di eventi COM tramite chiamate vtable ad associazione anticipata, ma sono supportate solo le chiamate `IDispatch::Invoke` ad associazione tardiva.

Se l'applicazione richiede chiamate ad associazione anticipata ai metodi dell'interfaccia di eventi COM, è possibile impostare la proprietà **Incorpora tipi di interoperabilità** di Visual Studio su `true` o includere l'elemento seguente nel file di progetto:

```xml
<EmbedInteropTypes>True</EmbedInteropTypes>
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [Wrapper COM](com-wrappers.md)
- [Esposizione di componenti .NET Framework a COM](../../framework/interop/exposing-dotnet-components-to-com.md)
- [Esposizione di componenti .NET Core a COM](../../core/native-interop/expose-components-to-com.md)
- [Qualificazione di tipi .NET per l'interoperabilità](qualify-net-types-for-interoperation.md)
- [Runtime Callable Wrapper](runtime-callable-wrapper.md)
