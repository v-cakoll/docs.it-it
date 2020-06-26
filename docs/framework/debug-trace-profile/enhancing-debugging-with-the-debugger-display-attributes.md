---
title: Miglioramento del debug tramite gli attributi di visualizzazione del debugger
description: Introduzione agli attributi di visualizzazione del debugger in .NET, che consentono allo sviluppatore del tipo di specificare anche l'aspetto del tipo quando viene visualizzato in un debugger.
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
ms.openlocfilehash: f266bf7278f472c51dd355df5ba04a123cbd7df0
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415966"
---
# <a name="enhancing-debugging-with-the-debugger-display-attributes"></a><span data-ttu-id="27618-103">Miglioramento del debug tramite gli attributi di visualizzazione del debugger</span><span class="sxs-lookup"><span data-stu-id="27618-103">Enhancing Debugging with the Debugger Display Attributes</span></span>

<span data-ttu-id="27618-104">Gli attributi di visualizzazione del debugger consentono allo sviluppatore del tipo, che specifica e conosce al meglio il comportamento di runtime di tale tipo, di specificare anche quale sarà l'aspetto del tipo quando verrà visualizzato in un debugger.</span><span class="sxs-lookup"><span data-stu-id="27618-104">Debugger display attributes allow the developer of the type, who specifies and best understands the runtime behavior of that type, to also specify what that type will look like when it is displayed in a debugger.</span></span> <span data-ttu-id="27618-105">Gli attributi di visualizzazione del debugger che forniscono una proprietà `Target` possono essere applicati a livello di assembly dagli utenti anche senza conoscere il codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="27618-105">In addition, debugger display attributes that provide a `Target` property can be applied at the assembly level by users without knowledge of the source code.</span></span> <span data-ttu-id="27618-106">L'attributo <xref:System.Diagnostics.DebuggerDisplayAttribute> controlla la modalità di visualizzazione di un tipo o di un membro nelle finestre delle variabili del debugger.</span><span class="sxs-lookup"><span data-stu-id="27618-106">The <xref:System.Diagnostics.DebuggerDisplayAttribute> attribute controls how a type or member is displayed in the debugger variable windows.</span></span> <span data-ttu-id="27618-107">L'attributo <xref:System.Diagnostics.DebuggerBrowsableAttribute> determina se e come un campo o una proprietà viene visualizzata nelle finestre delle variabili del debugger.</span><span class="sxs-lookup"><span data-stu-id="27618-107">The <xref:System.Diagnostics.DebuggerBrowsableAttribute> attribute determines if and how a field or property is displayed in the debugger variable windows.</span></span> <span data-ttu-id="27618-108">L'attributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> specifica un tipo sostituito, o proxy, per un tipo e modifica il modo in cui il tipo viene visualizzato nelle finestre del debugger.</span><span class="sxs-lookup"><span data-stu-id="27618-108">The <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attribute specifies a substitute type, or a proxy, for a type and changes the way the type is displayed in debugger windows.</span></span> <span data-ttu-id="27618-109">Quando si visualizza una variabile che ha un proxy, o tipo sostituito, il proxy prende il posto del tipo originale nella finestra di visualizzazione del debugger.</span><span class="sxs-lookup"><span data-stu-id="27618-109">When you view a variable that has a proxy, or substitute type, the proxy stands in for the original type in the debugger display window.</span></span> <span data-ttu-id="27618-110">Nella finestra delle variabili del debugger vengono visualizzati soltanto i membri pubblici del tipo proxy.</span><span class="sxs-lookup"><span data-stu-id="27618-110">The debugger variable window displays only the public members of the proxy type.</span></span> <span data-ttu-id="27618-111">I membri privati non vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="27618-111">Private members are not displayed.</span></span>  
  
## <a name="using-the-debuggerdisplayattribute"></a><span data-ttu-id="27618-112">Uso di DebuggerDisplayAttribute</span><span class="sxs-lookup"><span data-stu-id="27618-112">Using the DebuggerDisplayAttribute</span></span>  

<span data-ttu-id="27618-113">Il costruttore <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> presenta un solo argomento: una stringa da visualizzare nella colonna del valore per le istanze del tipo.</span><span class="sxs-lookup"><span data-stu-id="27618-113">The <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> constructor has a single argument: a string to be displayed in the value column for instances of the type.</span></span> <span data-ttu-id="27618-114">Questa stringa può contenere parentesi graffe ({ e }).</span><span class="sxs-lookup"><span data-stu-id="27618-114">This string can contain braces ({ and }).</span></span> <span data-ttu-id="27618-115">Il testo racchiuso tra due parentesi graffe viene valutato come espressione.</span><span class="sxs-lookup"><span data-stu-id="27618-115">The text within a pair of braces is evaluated as an expression.</span></span> <span data-ttu-id="27618-116">Il codice C# seguente, ad esempio, visualizza "Count = 4" quando viene selezionato il segno più (+) per espandere la visualizzazione del debugger per un'istanza di `MyHashtable`.</span><span class="sxs-lookup"><span data-stu-id="27618-116">For example, the following C# code causes "Count = 4" to be displayed when the plus sign (+) is selected to expand the debugger display for an instance of `MyHashtable`.</span></span>  

```csharp
[DebuggerDisplay("Count = {count}")]
class MyHashtable
{
    public int count = 4;
}
```

<span data-ttu-id="27618-117">Gli attributi applicati alle proprietà a cui si fa riferimento nell'espressione non vengono elaborati.</span><span class="sxs-lookup"><span data-stu-id="27618-117">Attributes applied to properties referenced in the expression are not processed.</span></span> <span data-ttu-id="27618-118">Per il compilatore C#, è consentita un'espressione generale che ha solo l'accesso implicito a questo riferimento per l'istanza corrente del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="27618-118">For the C# compiler, a general expression is allowed that has only implicit access to this reference for the current instance of the target type.</span></span> <span data-ttu-id="27618-119">L'espressione è limitata e non ha accesso ad alias, variabili locali o puntatori.</span><span class="sxs-lookup"><span data-stu-id="27618-119">The expression is limited; there is no access to aliases, locals, or pointers.</span></span> <span data-ttu-id="27618-120">Nel codice C# è possibile usare un'espressione generale tra parentesi graffe che ha accesso implicito al puntatore `this` solo per l'istanza corrente del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="27618-120">In C# code, you can use a general expression between the braces that has implicit access to the `this` pointer for the current instance of the target type only.</span></span>

<span data-ttu-id="27618-121">Se ad esempio un oggetto C# ha un metodo `ToString()` sottoposto a override, il debugger chiamerà l'override e ne visualizzerà il risultato, invece di chiamare il codice `{<typeName>}.` standard. Se quindi si è eseguito l'override di `ToString()`, non è necessario usare <xref:System.Diagnostics.DebuggerDisplayAttribute>.</span><span class="sxs-lookup"><span data-stu-id="27618-121">For example, if a C# object has an overridden `ToString()`, the debugger will call the override and show its result instead of the standard `{<typeName>}.` Thus, if you have overridden `ToString()`, you do not need to use <xref:System.Diagnostics.DebuggerDisplayAttribute>.</span></span> <span data-ttu-id="27618-122">Se si utilizzano entrambi, l'attributo <xref:System.Diagnostics.DebuggerDisplayAttribute> avrà la precedenza sull'override di `ToString()`.</span><span class="sxs-lookup"><span data-stu-id="27618-122">If you use both, the <xref:System.Diagnostics.DebuggerDisplayAttribute> attribute takes precedence over the `ToString()` override.</span></span>

## <a name="using-the-debuggerbrowsableattribute"></a><span data-ttu-id="27618-123">Uso di DebuggerBrowsableAttribute</span><span class="sxs-lookup"><span data-stu-id="27618-123">Using the DebuggerBrowsableAttribute</span></span>
 <span data-ttu-id="27618-124">Applicare <xref:System.Diagnostics.DebuggerBrowsableAttribute> a un campo o una proprietà per specificare come il campo o la proprietà deve essere visualizzata nella finestra del debugger.</span><span class="sxs-lookup"><span data-stu-id="27618-124">Apply the <xref:System.Diagnostics.DebuggerBrowsableAttribute> to a field or property to specify how the field or property is to be displayed in the debugger window.</span></span> <span data-ttu-id="27618-125">Il costruttore di questo attributo accetta uno dei valori di enumerazione <xref:System.Diagnostics.DebuggerBrowsableState>, che specifica uno degli stati seguenti:</span><span class="sxs-lookup"><span data-stu-id="27618-125">The constructor for this attribute takes one of the <xref:System.Diagnostics.DebuggerBrowsableState> enumeration values, which specifies one of the following states:</span></span>

- <span data-ttu-id="27618-126"><xref:System.Diagnostics.DebuggerBrowsableState.Never> indica che il membro non viene visualizzato nella finestra dei dati.</span><span class="sxs-lookup"><span data-stu-id="27618-126"><xref:System.Diagnostics.DebuggerBrowsableState.Never> indicates that the member is not displayed in the data window.</span></span>  <span data-ttu-id="27618-127">Ad esempio, usando questo valore per <xref:System.Diagnostics.DebuggerBrowsableAttribute> in un campo, il campo viene rimosso dalla gerarchia. Il campo non viene visualizzato quando si espande il tipo di inclusione facendo clic sul segno più (+) per l'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="27618-127">For example, using this value for the <xref:System.Diagnostics.DebuggerBrowsableAttribute> on a field removes the field from the hierarchy; the field is not displayed when you expand the enclosing type by clicking the plus sign (+) for the type instance.</span></span>

- <span data-ttu-id="27618-128"><xref:System.Diagnostics.DebuggerBrowsableState.Collapsed> indica che il membro viene visualizzato, ma non espanso per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="27618-128"><xref:System.Diagnostics.DebuggerBrowsableState.Collapsed> indicates that the member is displayed but not expanded by default.</span></span>  <span data-ttu-id="27618-129">Questo è il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="27618-129">This is the default behavior.</span></span>

- <span data-ttu-id="27618-130"><xref:System.Diagnostics.DebuggerBrowsableState.RootHidden> indica che non viene visualizzato il membro in sé, ma gli oggetti costituenti se è presente una matrice o una raccolta.</span><span class="sxs-lookup"><span data-stu-id="27618-130"><xref:System.Diagnostics.DebuggerBrowsableState.RootHidden> indicates that the member itself is not shown, but its constituent objects are displayed if it is an array or collection.</span></span>

> [!NOTE]
> <span data-ttu-id="27618-131"><xref:System.Diagnostics.DebuggerBrowsableAttribute> non è supportato da Visual Basic in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="27618-131">The <xref:System.Diagnostics.DebuggerBrowsableAttribute> is not supported by Visual Basic in the .NET Framework version 2.0.</span></span>

<span data-ttu-id="27618-132">L'esempio di codice seguente illustra l'uso di <xref:System.Diagnostics.DebuggerBrowsableAttribute> per impedire la visualizzazione della proprietà che lo segue nella finestra di debug della classe.</span><span class="sxs-lookup"><span data-stu-id="27618-132">The following code example shows the use of the <xref:System.Diagnostics.DebuggerBrowsableAttribute> to prevent the property following it from appearing in the debug window for the class.</span></span>

```csharp
[DebuggerBrowsable(DebuggerBrowsableState.Never)]
public static string y = "Test String";
```

## <a name="using-the-debuggertypeproxy"></a><span data-ttu-id="27618-133">Uso di DebuggerTypeProxy</span><span class="sxs-lookup"><span data-stu-id="27618-133">Using the DebuggerTypeProxy</span></span>
 <span data-ttu-id="27618-134">Usare l'attributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> quando è necessario modificare in modo significativo e sostanziale la visualizzazione di debug di un tipo, ma non il tipo in sé.</span><span class="sxs-lookup"><span data-stu-id="27618-134">Use the <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attribute when you need to significantly and fundamentally change the debugging view of a type, but not change the type itself.</span></span> <span data-ttu-id="27618-135">L'attributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> viene usato per specificare un proxy di visualizzazione per un tipo, consentendo a uno sviluppatore di personalizzare la vista per il tipo.</span><span class="sxs-lookup"><span data-stu-id="27618-135">The <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attribute is used to specify a display proxy for a type, allowing a developer to tailor the view for the type.</span></span>  <span data-ttu-id="27618-136">Questo attributo, come <xref:System.Diagnostics.DebuggerDisplayAttribute>, può essere usato a livello di assembly, nel qual caso la proprietà <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> specifica il tipo per cui il proxy verrà usato.</span><span class="sxs-lookup"><span data-stu-id="27618-136">This attribute, like the <xref:System.Diagnostics.DebuggerDisplayAttribute>, can be used at the assembly level, in which case the <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> property specifies the type for which the proxy will be used.</span></span> <span data-ttu-id="27618-137">L'utilizzo consigliato prevede che questo attributo specifichi un tipo annidato privato che viene generato nel tipo a cui l'attributo viene applicato.</span><span class="sxs-lookup"><span data-stu-id="27618-137">The recommended usage is that this attribute specifies a private nested type that occurs within the type to which the attribute is applied.</span></span>  <span data-ttu-id="27618-138">Un analizzatore di espressioni che supporta i visualizzatori di tipo cerca questo attributo quando viene visualizzato un tipo.</span><span class="sxs-lookup"><span data-stu-id="27618-138">An expression evaluator that supports type viewers checks for this attribute when a type is displayed.</span></span> <span data-ttu-id="27618-139">Se l'attributo viene trovato, l'analizzatore di espressioni sostituisce il tipo proxy di visualizzazione per il tipo a cui l'attributo viene applicato.</span><span class="sxs-lookup"><span data-stu-id="27618-139">If the attribute is found, the expression evaluator substitutes the display proxy type for the type the attribute is applied to.</span></span>

 <span data-ttu-id="27618-140">Quando <xref:System.Diagnostics.DebuggerTypeProxyAttribute> è presente, nella finestra delle variabili del debugger vengono visualizzati soltanto i membri pubblici del tipo proxy.</span><span class="sxs-lookup"><span data-stu-id="27618-140">When the <xref:System.Diagnostics.DebuggerTypeProxyAttribute> is present, the debugger variable window displays only the public members of the proxy type.</span></span> <span data-ttu-id="27618-141">I membri privati non vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="27618-141">Private members are not displayed.</span></span> <span data-ttu-id="27618-142">Il comportamento della finestra dei dati non viene modificato dalle visualizzazioni avanzate dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="27618-142">The behavior of the data window is not changed by attribute-enhanced views.</span></span>

 <span data-ttu-id="27618-143">Per evitare inutili conseguenze per le prestazioni, gli attributi del proxy di visualizzazione vengono elaborati solo dopo che l'oggetto viene espanso, tramite il clic da parte dell'utente sul segno più (+) accanto al tipo in una finestra di dati o tramite l'applicazione dell'attributo <xref:System.Diagnostics.DebuggerBrowsableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="27618-143">To avoid unnecessary performance penalties, attributes of the display proxy are not processed until the object is expanded, either through the user clicking the plus sign (+) next to the type in a data window, or through the application of the <xref:System.Diagnostics.DebuggerBrowsableAttribute> attribute.</span></span> <span data-ttu-id="27618-144">È quindi consigliabile non applicare attributi al tipo visualizzato.</span><span class="sxs-lookup"><span data-stu-id="27618-144">Therefore, it is recommended that no attributes be applied to the display type.</span></span> <span data-ttu-id="27618-145">È possibile e consigliabile applicare gli attributi nel corpo del tipo visualizzato.</span><span class="sxs-lookup"><span data-stu-id="27618-145">Attributes can and should be applied within the body of the display type.</span></span>

 <span data-ttu-id="27618-146">L'esempio di codice seguente illustra l'uso di <xref:System.Diagnostics.DebuggerTypeProxyAttribute> per specificare un tipo da usare come proxy di visualizzazione del debugger.</span><span class="sxs-lookup"><span data-stu-id="27618-146">The following code example shows the use of the <xref:System.Diagnostics.DebuggerTypeProxyAttribute> to specify a type to be used as a debugger display proxy.</span></span>

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

## <a name="example"></a><span data-ttu-id="27618-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="27618-147">Example</span></span>

### <a name="description"></a><span data-ttu-id="27618-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27618-148">Description</span></span>

<span data-ttu-id="27618-149">L'esempio di codice seguente può essere visualizzato in Visual Studio per visualizzare i risultati dell'applicazione <xref:System.Diagnostics.DebuggerDisplayAttribute> degli <xref:System.Diagnostics.DebuggerBrowsableAttribute> attributi, e <xref:System.Diagnostics.DebuggerTypeProxyAttribute> .</span><span class="sxs-lookup"><span data-stu-id="27618-149">The following code example can be viewed in Visual Studio to see the results of applying the <xref:System.Diagnostics.DebuggerDisplayAttribute>, <xref:System.Diagnostics.DebuggerBrowsableAttribute>, and <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attributes.</span></span>

### <a name="code"></a><span data-ttu-id="27618-150">Codice</span><span class="sxs-lookup"><span data-stu-id="27618-150">Code</span></span>

[!code-cpp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/cpp/program.cpp#1)]
[!code-csharp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/CS/program.cs#1)]
[!code-vb[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/VB/module1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="27618-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27618-151">See also</span></span>

- <xref:System.Diagnostics.DebuggerDisplayAttribute>
- <xref:System.Diagnostics.DebuggerBrowsableAttribute>
- <xref:System.Diagnostics.DebuggerTypeProxyAttribute>
