---
title: Miglioramento del debug tramite gli attributi di visualizzazione del debugger
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- debugger, display attributes
- DebuggerTypeProxyAttribute attribute
- debugging [.NET Framework], debugger display attributes
- DebuggerDisplayAttribute attribute
- display attributes for debugger
- DebuggerBrowsableAttribute attribute
ms.assetid: 72bb7aa9-459b-42c4-9163-9312fab4c410
ms.openlocfilehash: ca118bffb045a0e7e3a5084916a0ff8020ebda90
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216498"
---
# <a name="enhancing-debugging-with-the-debugger-display-attributes"></a>Miglioramento del debug tramite gli attributi di visualizzazione del debugger

Gli attributi di visualizzazione del debugger consentono allo sviluppatore del tipo, che specifica e conosce al meglio il comportamento di runtime di tale tipo, di specificare anche quale sarà l'aspetto del tipo quando verrà visualizzato in un debugger. Gli attributi di visualizzazione del debugger che forniscono una proprietà `Target` possono essere applicati a livello di assembly dagli utenti anche senza conoscere il codice sorgente. L'attributo <xref:System.Diagnostics.DebuggerDisplayAttribute> controlla la modalità di visualizzazione di un tipo o di un membro nelle finestre delle variabili del debugger. L'attributo <xref:System.Diagnostics.DebuggerBrowsableAttribute> determina se e come un campo o una proprietà viene visualizzata nelle finestre delle variabili del debugger. L'attributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> specifica un tipo sostituito, o proxy, per un tipo e modifica il modo in cui il tipo viene visualizzato nelle finestre del debugger. Quando si visualizza una variabile con un proxy o un tipo di sostituzione, il proxy si trova in per il tipo originale nella finestra di visualizzazione del debugger. Nella finestra delle variabili del debugger vengono visualizzati soltanto i membri pubblici del tipo proxy. I membri privati non vengono visualizzati.  
  
## <a name="using-the-debuggerdisplayattribute"></a>Uso di DebuggerDisplayAttribute  

Il costruttore <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> presenta un solo argomento: una stringa da visualizzare nella colonna del valore per le istanze del tipo. Questa stringa può contenere parentesi graffe ({ e }). Il testo racchiuso tra due parentesi graffe viene valutato come espressione. Il codice C# seguente, ad esempio, visualizza "Count = 4" quando viene selezionato il segno più (+) per espandere la visualizzazione del debugger per un'istanza di `MyHashtable`.  

```csharp
[DebuggerDisplay("Count = {count}")]
class MyHashtable
{
    public int count = 4;
}
```

Gli attributi applicati alle proprietà a cui si fa riferimento nell'espressione non vengono elaborati. Per il compilatore C#, è consentita un'espressione generale che ha solo l'accesso implicito a questo riferimento per l'istanza corrente del tipo di destinazione. L'espressione è limitata e non ha accesso ad alias, variabili locali o puntatori. Nel codice C# è possibile usare un'espressione generale tra parentesi graffe che ha accesso implicito al puntatore `this` solo per l'istanza corrente del tipo di destinazione.

Se ad esempio un oggetto C# ha un metodo `ToString()` sottoposto a override, il debugger chiamerà l'override e ne visualizzerà il risultato, invece di chiamare il codice `{<typeName>}.` standard. Se quindi si è eseguito l'override di `ToString()`, non è necessario usare <xref:System.Diagnostics.DebuggerDisplayAttribute>. Se si utilizzano entrambi, l'attributo <xref:System.Diagnostics.DebuggerDisplayAttribute> avrà la precedenza sull'override di `ToString()`.

## <a name="using-the-debuggerbrowsableattribute"></a>Uso di DebuggerBrowsableAttribute
 Applicare <xref:System.Diagnostics.DebuggerBrowsableAttribute> a un campo o una proprietà per specificare come il campo o la proprietà deve essere visualizzata nella finestra del debugger. Il costruttore di questo attributo accetta uno dei valori di enumerazione <xref:System.Diagnostics.DebuggerBrowsableState>, che specifica uno degli stati seguenti:

- <xref:System.Diagnostics.DebuggerBrowsableState.Never> indica che il membro non viene visualizzato nella finestra dei dati.  Ad esempio, usando questo valore per <xref:System.Diagnostics.DebuggerBrowsableAttribute> in un campo, il campo viene rimosso dalla gerarchia. Il campo non viene visualizzato quando si espande il tipo di inclusione facendo clic sul segno più (+) per l'istanza del tipo.

- <xref:System.Diagnostics.DebuggerBrowsableState.Collapsed> indica che il membro viene visualizzato, ma non espanso per impostazione predefinita.  Questo è il comportamento predefinito.

- <xref:System.Diagnostics.DebuggerBrowsableState.RootHidden> indica che non viene visualizzato il membro in sé, ma gli oggetti costituenti se è presente una matrice o una raccolta.

> [!NOTE]
> <xref:System.Diagnostics.DebuggerBrowsableAttribute> non è supportato da Visual Basic in .NET Framework versione 2.0.

L'esempio di codice seguente illustra l'uso di <xref:System.Diagnostics.DebuggerBrowsableAttribute> per impedire la visualizzazione della proprietà che lo segue nella finestra di debug della classe.

```csharp
[DebuggerBrowsable(DebuggerBrowsableState.Never)]
public static string y = "Test String";
```

## <a name="using-the-debuggertypeproxy"></a>Uso di DebuggerTypeProxy
 Usare l'attributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> quando è necessario modificare in modo significativo e sostanziale la visualizzazione di debug di un tipo, ma non il tipo in sé. L'attributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> viene usato per specificare un proxy di visualizzazione per un tipo, consentendo a uno sviluppatore di personalizzare la vista per il tipo.  Questo attributo, come <xref:System.Diagnostics.DebuggerDisplayAttribute>, può essere usato a livello di assembly, nel qual caso la proprietà <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> specifica il tipo per cui il proxy verrà usato. L'utilizzo consigliato prevede che questo attributo specifichi un tipo annidato privato che viene generato nel tipo a cui l'attributo viene applicato.  Un analizzatore di espressioni che supporta i visualizzatori di tipo cerca questo attributo quando viene visualizzato un tipo. Se l'attributo viene trovato, l'analizzatore di espressioni sostituisce il tipo proxy di visualizzazione per il tipo a cui l'attributo viene applicato.

 Quando <xref:System.Diagnostics.DebuggerTypeProxyAttribute> è presente, nella finestra delle variabili del debugger vengono visualizzati soltanto i membri pubblici del tipo proxy. I membri privati non vengono visualizzati. Il comportamento della finestra dei dati non viene modificato dalle visualizzazioni avanzate dell'attributo.

 Per evitare inutili conseguenze per le prestazioni, gli attributi del proxy di visualizzazione vengono elaborati solo dopo che l'oggetto viene espanso, tramite il clic da parte dell'utente sul segno più (+) accanto al tipo in una finestra di dati o tramite l'applicazione dell'attributo <xref:System.Diagnostics.DebuggerBrowsableAttribute>. È quindi consigliabile non applicare attributi al tipo visualizzato. È possibile e consigliabile applicare gli attributi nel corpo del tipo visualizzato.

 L'esempio di codice seguente illustra l'uso di <xref:System.Diagnostics.DebuggerTypeProxyAttribute> per specificare un tipo da usare come proxy di visualizzazione del debugger.

```csharp
[DebuggerTypeProxy(typeof(HashtableDebugView))]
class MyHashtable : Hashtable
{
    private const string TestString =
        "This should not appear in the debug window.";

    internal class HashtableDebugView
    {
        private Hashtable hashtable;
        public const string TestStringProxy =
            "This should appear in the debug window.";

        // The constructor for the type proxy class must have a
        // constructor that takes the target type as a parameter.
        public HashtableDebugView(Hashtable hashtable)
        {
            this.hashtable = hashtable;
        }
    }
}
```

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione

L'esempio di codice seguente può essere visualizzato in Visual Studio per visualizzare i risultati dell'applicazione degli attributi <xref:System.Diagnostics.DebuggerDisplayAttribute>, <xref:System.Diagnostics.DebuggerBrowsableAttribute>e <xref:System.Diagnostics.DebuggerTypeProxyAttribute>.

### <a name="code"></a>Codice

[!code-cpp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/cpp/program.cpp#1)]
[!code-csharp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/CS/program.cs#1)]
[!code-vb[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/VB/module1.vb#1)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Diagnostics.DebuggerDisplayAttribute>
- <xref:System.Diagnostics.DebuggerBrowsableAttribute>
- <xref:System.Diagnostics.DebuggerTypeProxyAttribute>
