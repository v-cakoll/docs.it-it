---
title: Semantica di riferimento con tipi di valore
description: "Comprendere le funzionalità del linguaggio che riducono al minimo la copia di strutture in modo sicuro"
author: billwagner
ms.author: wiwagn
ms.date: 11/10/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 9eeaf201c1f5a58044db62e356199b609c4c035a
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="reference-semantics-with-value-types"></a>Semantica di riferimento con tipi di valore

Un vantaggio dell'utilizzo di tipi di valore è spesso evitare allocazioni di heap.
Lo svantaggio corrispondente è che vengono copiati dal valore. Questo compromesso rende più difficile ottimizzare gli algoritmi che operano su grandi quantità di dati. Nuove funzionalità del linguaggio c# 7.2 fornire meccanismi che consentano la semantica di passaggio per riferimento con tipi di valore. Se si utilizzano queste funzionalità in modo appropriato, è possibile ridurre al minimo entrambe le allocazioni e operazioni di copia. Questo articolo esamina le nuove funzionalità.

Gran parte del codice di esempio in questo articolo illustra le funzionalità aggiunte in c# 7.2. Per utilizzare queste funzionalità, è necessario configurare il progetto per l'utilizzo di c# 7.2 o versione successiva nel progetto. È possibile utilizzare Visual Studio per selezionarlo. Per ogni progetto, selezionare **progetto** dal menu, quindi **proprietà**. Selezionare il **compilare** scheda e fare clic su **avanzate**. Da qui, è possibile configurare la versione in lingua. Selezionare "7.2" o "più recente".  È possibile modificare il *csproj* file e aggiungere il nodo seguente:

```XML
  <PropertyGroup>
    <LangVersion>7.2</LangVersion>
  </PropertyGroup>
```

È possibile utilizzare "7,2" o "più recente" per il valore.

## <a name="specifying-in-parameters"></a>Specifica di `in` parametri

7.2 c# aggiunge il `in` (parola chiave) per integrare esistente `ref` e `out` parole chiave quando si scrive un metodo che passa gli argomenti per riferimento. Il `in` (parola chiave) specifica che si passa il parametro per riferimento e il metodo chiamato non modifica il valore passato. 

In questo modo fornisce un vocabolario completo per esprimere la finalità di progettazione. Tipi di valore vengono copiati quando viene passato a un metodo chiamato quando non si specifica uno dei seguenti modificatori. Ognuno di questi modificatori di specificare un tipo di valore viene passato per riferimento, di copia. Ogni modificatore esprime diversi:

- `out`: Questo metodo imposta il valore dell'argomento utilizzato come questo parametro.
- `ref`: Questo metodo consente di impostare il valore dell'argomento utilizzato come questo parametro.
- `in`: Questo metodo non modifica il valore dell'argomento utilizzato come questo parametro.

Quando si aggiunge il `in` modificatore per passare un argomento per riferimento, si dichiara la finalità di progettazione consiste nel passare argomenti per riferimento per evitare la copia non necessarie. Non si intende modificare l'oggetto utilizzato come argomento. Il codice seguente viene illustrato un esempio di un metodo che calcola la distanza tra due punti nello spazio 3D. 

[!code-csharp[InArgument](../../samples/csharp/reference-semantics/Program.cs#InArgument "Specifying an In argument")]

Gli argomenti sono due strutture di ciascuno dei quali contiene tre valori Double. Un valore double è di 8 byte, pertanto ogni argomento è di 24 byte. Specificando il `in` modificatore, passare 4 o 8 byte riferimento a tali argomenti, a seconda dell'architettura del computer. Differenza nella dimensione è ridotto, ma è possibile aggiungere rapidamente quando l'applicazione chiama questo metodo in un ciclo rigido utilizzando molti valori diversi.
 
Il `in` modificatore integra `out` e `ref` in anche altri modi. Non è possibile creare gli overload di un metodo che differiscono solo in presenza di `in`, `out` o `ref`. Queste nuove regole di estendono lo stesso comportamento che sempre fosse stato definito per `out` e `ref` parametri.

Il `in` modificatore può essere applicato a qualsiasi membro che accetta parametri: metodi, delegati, le espressioni lambda, le funzioni locali, gli indicizzatori, gli operatori.

A differenza di `ref` e `out` argomenti, è possibile utilizzare valori letterali o le costanti per l'argomento di un `in` parametro. Inoltre, a differenza di un `ref` o `out` parametro, non è necessario applicare il `in` modificatore nel sito di chiamata. Il codice seguente mostra due esempi di chiamata di `CalculateDistance` metodo. Il primo usa due variabili locali, passate per riferimento. Il secondo include una variabile temporanea creata come parte della chiamata al metodo. 

[!code-csharp[UseInArgument](../../samples/csharp/reference-semantics/Program.cs#UseInArgument "Specifying an In argument")]

Esistono diversi modi in cui il compilatore garantisce che la natura di sola lettura di un `in` viene applicato l'argomento.  Prima di tutto, il metodo chiamato non è possibile assegnare direttamente un `in` parametro. È possibile assegnare direttamente a qualsiasi campo di un `in` parametro. Inoltre, non è possibile passare un `in` parametro alle eventuali rigorose del metodo di `ref` o `out` modificatore.
Il compilatore impone che il `in` argomento è una variabile di sola lettura. È possibile chiamare qualsiasi metodo di istanza che utilizza la semantica pass-by-value. In tali casi, una copia del `in` parametro viene creato. Poiché il compilatore può creare una variabile temporanea per qualsiasi `in` parametro, è anche possibile specificare i valori predefiniti per qualsiasi `in` parametro. Nel codice seguente che usa per specificare l'origine (punto 0,0) come valore predefinito per il secondo punto:

[!code-csharp[InArgumentDefault](../../samples/csharp/reference-semantics/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

Il `in` designazione di parametro può essere utilizzata con tipi di riferimento o compilazione nei valori numerici. Tuttavia, i vantaggi in entrambi i casi sono minimi, se presente.

## <a name="ref-readonly-returns"></a>`ref readonly`Restituisce

È anche possibile restituire un tipo di valore per riferimento, ma non consentire al chiamante di modificare tale valore. Utilizzare il `ref readonly` modificatore per esprimere la finalità di progettazione. Invia una notifica a lettori che restituisce un riferimento ai dati esistenti, ma non consente la modifica. 

Il compilatore impone che il chiamante non è possibile modificare il riferimento. Tenta di assegnare direttamente il valore generato un errore in fase di compilazione. Tuttavia, il compilatore non sa se qualsiasi metodo di membro viene modificato lo stato dello struct.
Per garantire che l'oggetto non viene modificato, il compilatore crea una copia e chiama membro riferimenti utilizzando tale copia. Tutte le modifiche sono a tale copia difensivo. 

È probabile che la libreria utilizzando `Point3D` spesso utilizzerebbe l'origine in tutto il codice. Ogni istanza crea un nuovo oggetto nello stack. Può risultare utile per creare una costante e viene restituito per riferimento. Tuttavia, se si restituisce un riferimento all'archiviazione interna, si desidera imporre che il chiamante non è possibile modificare lo spazio di archiviazione a cui fa riferimento. Il codice seguente definisce una proprietà di sola lettura che restituisce un `readonly ref` per un `Point3D` che specifica l'origine.

[!code-csharp[OriginReference](../../samples/csharp/reference-semantics/Point3D.cs#OriginReference "Creating a readonly Origin reference")]

Creazione di una copia di un riferimento di sola lettura restituito è semplice: assegna semplicemente a una variabile non è dichiarata con la `ref readonly` modificatore. Il compilatore genera codice per copiare l'oggetto come parte dell'assegnazione. 

Quando si assegna una variabile per un `ref readonly return`, è possibile specificare un `ref readonly` variabile o una copia in base al valore del riferimento di sola lettura:

[!code-csharp[AssignRefReadonly](../../samples/csharp/reference-semantics/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

Copia la prima assegnazione nel codice precedente il `Origin` costante e assegna tale copia. Il secondo consente di assegnare un riferimento. Si noti che il `readonly` modificatore deve essere parte della dichiarazione della variabile. Il riferimento a cui viene fatto riferimento non può essere modificato. I tentativi di eseguire questa operazione generano un errore in fase di compilazione.

## <a name="readonly-struct-type"></a>Tipo `readonly struct`

L'applicazione `ref readonly` a traffico elevato utilizzi di uno struct, potrebbe essere sufficiente.
In altri casi, è consigliabile creare un struct non modificabile. È sempre possibile passare per riferimento di sola lettura. Di norma rimuove difensiva copia che si verificano quando si accede ai metodi di una struttura utilizzata come un `in` parametro.

È possibile farlo creando un `readonly struct` tipo. È possibile aggiungere il `readonly` modificatore in una dichiarazione di struttura. Il compilatore impone che tutti i membri dello struct sono `readonly`; `struct` deve essere non modificabile.

Sono disponibili altre ottimizzazioni per un `readonly struct`. È possibile utilizzare il `in` modificatore in qualunque posizione in cui un `readonly struct` è un argomento. Inoltre, è possibile restituire un `readonly struct` come un `ref return` quando viene restituito un oggetto la cui durata si estende oltre l'ambito del metodo restituisce l'oggetto.

Infine, il compilatore genera codice più efficiente quando si chiamano i membri di un `readonly struct`: il `this` riferimento, anziché una copia del ricevitore, è sempre un `in` parametro passato per riferimento al metodo del membro. Questa ottimizzazione consente di salvare la copia più quando si utilizza un `readonly struct`. Il `Point3D` è un ottimo candidato per la modifica. Nel codice seguente viene aggiornata `ReadonlyPoint3D` struttura:

[!code-csharp[ReadonlyOnlyPoint3D](../../samples/csharp/reference-semantics/Point3D.cs#ReadonlyOnlyPoint3D "Defining an immutable structure")]

## <a name="ref-struct-type"></a>Tipo `ref struct`

Un'altra funzionalità del linguaggio correlato è la possibilità di dichiarare un tipo di valore che deve essere allocato nello stack. In altre parole, questi tipi non possono mai essere creati nell'heap come membro di un'altra classe. La principale motivazione per questa funzionalità è stata <xref:System.Span%601> e strutture correlate. <xref:System.Span%601>contenga un puntatore gestito come uno dei relativi membri, mentre l'altro è la lunghezza dell'intervallo. È effettivamente implementata in modo leggermente diverso perché c# non supporta i puntatori alla memoria gestita di fuori di un contesto unsafe. Qualsiasi scrittura che modifica il puntatore del mouse e la lunghezza non è atomico. Ciò significa che un <xref:System.Span%601> sarà soggetto a errori di intervallo insufficiente o altre violazioni di sicurezza di tipo sono stati non è vincolato da un unico stack frame. Inoltre, l'inserimento di un puntatore gestito nell'heap GC in genere si blocca in fase di JIT.

È possibile requisiti simili operazioni con la memoria creata utilizzando [ `stackalloc` ](language-reference/keywords/stackalloc.md) o quando si utilizza memoria dalle API di interoperabilità. È possibile definire `ref struct` tipi per tali requisiti. In questo articolo si vedere esempi di utilizzo `Span<T>` per semplicità.

Il `ref struct` dichiarazione dichiara che una struttura di questo tipo deve essere nello stack. Le regole del linguaggio verificare l'utilizzo sicuro di questi tipi. Altri tipi dichiarati come `ref struct` includono <xref:System.ReadOnlySpan%601>. 

L'obiettivo di mantenere un `ref struct` digitare come una variabile allocato dallo stack introduce diverse regole che il compilatore impone per tutti i `ref struct` tipi.

- Non supporta il boxing è una `ref struct`. Non è possibile assegnare un `ref struct` tipo a una variabile di tipo `object`, `dynamic`, o qualsiasi tipo di interfaccia.
- Non è possibile dichiarare un `ref struct` come membro di una classe o uno struct normale.
- Non è possibile dichiarare le variabili locali con `ref struct` tipi di metodi asincroni. È possibile dichiararli in metodi sincroni che restituiscono `Task`, `Task<T>` o tipi di attività.
- Non è possibile dichiarare `ref struct` variabili locali, gli iteratori.
- Non è possibile acquisire `ref struct` variabili nelle espressioni lambda o di funzioni locali.

In questo modo che non si accidentalmente utilizza un `ref struct` in modo che è stato possibile alzare di livello per l'heap gestito.

## <a name="conclusions"></a>Conclusioni

Questi miglioramenti del linguaggio c# sono progettati per gli algoritmi di prestazioni critiche in cui le allocazioni di memoria possono essere fondamentale per ottenere le prestazioni necessarie. È possibile che non vengano utilizzati spesso queste funzionalità nel codice che scritto. Tuttavia, questi miglioramenti sono stati adottati in numerose posizioni in .NET Framework. Come rendere più API utilizzare queste funzionalità, si noterà un' migliorare le prestazioni delle applicazioni.
