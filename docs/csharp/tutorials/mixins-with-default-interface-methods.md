---
title: Creare tipi mixin utilizzando i metodi di interfaccia predefiniti
description: Utilizzando i membri di interfaccia predefiniti è possibile estendere le interfacce con implementazioni predefinite facoltative per gli implementatori.
ms.technology: csharp-advanced-concepts
ms.date: 10/04/2019
ms.openlocfilehash: ee0536ef51f9bea3e6851be23cc19fa28cc6916b
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134370"
---
# <a name="tutorial-mix-functionality-in-when-creating-classes-using-interfaces-with-default-interface-methods"></a>Esercitazione: Combinare funzionalità quando si creano classi utilizzando interfacce con metodi di interfaccia predefinitiTutorial: Mix functionality in when creating classes using interfaces with default interface methods

A partire da C# 8.0 su .NET Core 3.0 è possibile definire un'implementazione quando si dichiara un membro di un'interfaccia. Questa funzionalità offre nuove funzionalità in cui è possibile definire implementazioni predefinite per le funzionalità dichiarate nelle interfacce. Le classi possono scegliere quando eseguire l'override della funzionalità, quando utilizzare la funzionalità predefinita e quando non dichiarare il supporto per funzionalità discrete.

In questa esercitazione si apprenderà come:

> [!div class="checklist"]
>
> * Creare interfacce con implementazioni che descrivono funzionalità discrete.
> * Creare classi che utilizzano le implementazioni predefinite.
> * Creare classi che eseguono l'override di alcune o tutte le implementazioni predefinite.

## <a name="prerequisites"></a>Prerequisiti

È necessario configurare il computer per l'esecuzione di .NET Core, incluso il compilatore c'è 8.0. È disponibile il compilatore di C'è 8.0 a partire da [Visual Studio 2019 versione 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)o [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) o versione successiva.

## <a name="limitations-of-extension-methods"></a>Limitazioni dei metodi di estensione

Un modo per implementare il comportamento che viene visualizzato come parte di un'interfaccia consiste nel definire [i metodi](../programming-guide/classes-and-structs/extension-methods.md) di estensione che forniscono il comportamento predefinito. Le interfacce dichiarano un set minimo di membri fornendo allo stesso tempo un'area di superficie maggiore per qualsiasi classe che implementa tale interfaccia. Ad esempio, i <xref:System.Linq.Enumerable> metodi di estensione in forniscono l'implementazione per qualsiasi sequenza come origine di una query LINQ.

I metodi di estensione vengono risolti in fase di compilazione, utilizzando il tipo dichiarato della variabile. Le classi che implementano l'interfaccia possono fornire un'implementazione migliore per qualsiasi metodo di estensione. Le dichiarazioni di variabili devono corrispondere al tipo di implementazione per consentire al compilatore di scegliere tale implementazione. Quando il tipo in fase di compilazione corrisponde all'interfaccia, le chiamate al metodo resolve nel metodo di estensione. Un altro problema con i metodi di estensione è che tali metodi sono accessibili ovunque la classe contenente i metodi di estensione è accessibile. Le classi non possono dichiarare se devono o non devono fornire funzionalità dichiarate nei metodi di estensione.

A partire dalla versione 8.0 di C, è possibile dichiarare le implementazioni predefinite come metodi di interfaccia. Quindi, ogni classe utilizza automaticamente l'implementazione predefinita. Qualsiasi classe che può fornire un'implementazione migliore può eseguire l'override della definizione del metodo di interfaccia con un algoritmo migliore. In un certo senso, questa tecnica suona simile a come è possibile utilizzare [i metodi](../programming-guide/classes-and-structs/extension-methods.md)di estensione .

In questo articolo verrà illustrato come le implementazioni predefinite dell'interfaccia consentono nuovi scenari.

## <a name="design-the-application"></a>Progettare l'applicazione

Si consideri un'applicazione di domotica. Probabilmente hai molti tipi diversi di luci e indicatori che potrebbero essere utilizzati in tutta la casa. Ogni luce deve supportare le API per attivarle e disattivarle e per segnalare lo stato corrente. Alcune luci e indicatori possono supportare altre funzionalità, ad esempio:

- Accendere la luce, quindi spegnerla dopo un timer.
- Lampeggiare la luce per un certo periodo di tempo.

Alcune di queste funzionalità estese potrebbero essere emulate nei dispositivi che supportano il set minimo. Ciò indica fornire un'implementazione predefinita. Per i dispositivi con più funzionalità incorporate, il software del dispositivo utilizzerebbe le funzionalità native. Per altre luci, è possibile scegliere di implementare l'interfaccia e utilizzare l'implementazione predefinita.

I membri di interfaccia predefiniti sono una soluzione migliore per questo scenario rispetto ai metodi di estensione. Gli autori di classi possono controllare quali interfacce scegliere di implementare. Le interfacce che scelgono sono disponibili come metodi. Inoltre, poiché i metodi di interfaccia predefiniti sono virtuali per impostazione predefinita, l'invio del metodo sceglie sempre l'implementazione nella classe.

Creiamo il codice per dimostrare queste differenze.

## <a name="create-interfaces"></a>Creare interfacce

Iniziare creando l'interfaccia che definisce il comportamento per tutte le luci:

[!code-csharp[Declare base interface](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/UnusedExampleCode.cs?name=SnippetILightInterfaceV1)]

Un dispositivo di illuminazione overhead di base potrebbe implementare questa interfaccia come illustrato nel codice seguente:A basic overhead light fixture might implement this interface as shown in the following code:

[!code-csharp[First overhead light](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/UnusedExampleCode.cs?name=SnippetOverheadLightV1)]

In questa esercitazione il codice non gestisce i dispositivi IoT, ma emula tali attività scrivendo messaggi nella console. È possibile esplorare il codice senza automatizzare la vostra casa.

Successivamente, definiamo l'interfaccia per una luce che può spegnersi automaticamente dopo un timeout:

[!code-csharp[pure Timer interface](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/UnusedExampleCode.cs?name=SnippetPureTimerInterface)]

È possibile aggiungere un'implementazione di base alla luce dell'overhead, `virtual` ma una soluzione migliore consiste nel modificare questa definizione di interfaccia per fornire un'implementazione predefinita:You could add a basic implementation to the overhead light, but a better solution is to modify this interface definition to provide a default implementation:

[!code-csharp[Timer interface](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/ITimerLight.cs?name=SnippetTimerLightFinal)]

Aggiungendo tale modifica, `OverheadLight` la classe può implementare la funzione timer dichiarando il supporto per l'interfaccia:By adding that change, the class can implement the timer function by declaring support for the interface:

```csharp
public class OverheadLight : ITimerLight { }
```

Un tipo di luce diverso può supportare un protocollo più sofisticato. Può fornire la propria `TurnOnFor`implementazione per , come illustrato nel codice seguente:

[!code-csharp[Override the timer function](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/HalogenLight.cs?name=SnippetHalogenLight)]

A differenza dell'override `TurnOnFor` `HalogenLight` dei metodi della classe virtuale, la dichiarazione di nella classe non utilizza la `override` parola chiave .

## <a name="mix-and-match-capabilities"></a>Funzionalità di miscelare e abbinare

I vantaggi dei metodi di interfaccia predefiniti diventano più chiari man mano che si introducono funzionalità più avanzate. L'utilizzo delle interfacce consente di combinare e abbinare le funzionalità. Consente inoltre a ogni autore di classi di scegliere tra l'implementazione predefinita e un'implementazione personalizzata. Aggiungiamo un'interfaccia con un'implementazione predefinita per una luce lampeggiante:Let's add an interface with a default implementation for a blinking light:

[!code-csharp[Define the blinking light interface](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/IBlinkingLight.cs?name=SnippetBlinkingLight)]

L'implementazione predefinita consente a qualsiasi luce di lampeggiare. La luce dell'overhead può aggiungere funzionalità timer e lampeggiante utilizzando l'implementazione predefinita:The overhead light can add both timer and blink capabilities using the default implementation:

[!code-csharp[Use the default blink function](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/OverheadLight.cs?name=SnippetOverheadLight)]

Un nuovo tipo `LEDLight` di luce, supporta sia la funzione timer che la funzione lampeggiante direttamente. Questo stile di `ITimerLight` luce `IBlinkingLight` implementa entrambe le `Blink` interfacce e esegue l'override del metodo:

[!code-csharp[Override the blink function](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/LEDLight.cs?name=SnippetLEDLight)]

Un `ExtraFancyLight` potrebbe supportare direttamente le funzioni lampeggiante e timer:

[!code-csharp[Override the blink and timer function](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/ExtraFancyLight.cs?name=SnippetExtraFancyLight)]

Il `HalogenLight` creato in precedenza non supporta l'lampeggiamento. Quindi, non aggiungere `IBlinkingLight` l'oggetto all'elenco delle interfacce supportate.

## <a name="detect-the-light-types-using-pattern-matching"></a>Rilevare i tipi di luce utilizzando criteri di ricerca

Successivamente, scriviamo del codice di test. È possibile utilizzare la funzionalità di [criteri di ricerca](../pattern-matching.md) di C , per determinare le funzionalità di una luce esaminando le interfacce supportate.  Il metodo seguente esercita le funzionalità supportate di ogni luce:

[!code-csharp[Test a light's capabilities](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/Program.cs?name=SnippetTestLightFunctions)]

Il codice seguente `Main` nel metodo crea ogni tipo di luce in sequenza e verifica tale luce:The following code in your method creates each light type in sequence and tests that light:

[!code-csharp[Test a light's capabilities](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/Program.cs?name=SnippetMainMethod)]

## <a name="how-the-compiler-determines-best-implementation"></a>Come il compilatore determina la migliore implementazione

Questo scenario mostra un'interfaccia di base senza implementazioni. L'aggiunta di `ILight` un metodo nell'interfaccia introduce nuove complessità. Le regole del linguaggio che regolano i metodi di interfaccia predefiniti riducono al minimo l'effetto sulle classi concrete che implementano più interfacce derivate. Cerchiamo di migliorare l'interfaccia originale con un nuovo metodo per mostrare come che cambia il suo utilizzo. Ogni indicatore luminoso può segnalare il suo stato di alimentazione come un valore enumerato:

[!code-csharp[Enumeration for power status](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/ILight.cs?name=SnippetPowerStatus)]

L'implementazione predefinita non presuppone alimentazione:The default implementation assumes no power:

[!code-csharp[Report a default power status](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/ILight.cs?name=SnippetILightInterface)]

Queste modifiche vengono compilate `ExtraFancyLight` correttamente, anche `ILight` se dichiara il `ITimerLight` supporto `IBlinkingLight`per l'interfaccia ed entrambe le interfacce derivate e . C'è solo un'implementazione "più vicina" dichiarata nell'interfaccia. `ILight` Qualsiasi classe che ha dichiarato un override diventerebbe l'implementazione "più vicina". Sono stati illustrati esempi nelle classi precedenti che hanno eseguito l'override dei membri di altre interfacce derivate.

Evitare di eseguire l'override dello stesso metodo in più interfacce derivate. In questo modo viene creata una chiamata al metodo ambigua ogni volta che una classe implementa entrambe le interfacce derivate. Il compilatore non è in grado di scegliere un singolo metodo migliore, pertanto genera un errore. Ad esempio, se `IBlinkingLight` `ITimerLight` sia il `PowerStatus`e `OverheadLight` implementato un override di , sarà necessario fornire un override più specifico. In caso contrario, il compilatore non può scegliere tra le implementazioni nelle due interfacce derivate. In genere è possibile evitare questa situazione mantenendo le definizioni di interfaccia piccole e focalizzate su una funzionalità. In questo scenario, ogni capacità di una luce è la propria interfaccia; più interfacce vengono ereditate solo dalle classi.

In questo esempio viene illustrato uno scenario in cui è possibile definire funzionalità discrete che possono essere mescolate in classi. Dichiarare qualsiasi set di funzionalità supportate dichiarando quali interfacce supporta una classe. L'utilizzo di metodi di interfaccia predefinita virtuali consente alle classi di utilizzare o definire un'implementazione diversa per uno o tutti i metodi di interfaccia. Questa funzionalità del linguaggio offre nuovi modi per modellare i sistemi reali che si stanno creando. I metodi di interfaccia predefiniti forniscono un modo più chiaro per esprimere le classi correlate che possono combinare e abbinare funzionalità diverse utilizzando implementazioni virtuali di tali funzionalità.
