---
title: Creare tipi mixin usando metodi di interfaccia predefiniti
description: Utilizzando i membri di interfaccia predefiniti è possibile estendere le interfacce con implementazioni predefinite facoltative per gli implementatori.
ms.technology: csharp-advanced-concepts
ms.date: 10/04/2019
ms.openlocfilehash: aaf8d34e27c9c56d95560656eb7a7b24b152c053
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78240106"
---
# <a name="tutorial-mix-functionality-in-when-creating-classes-using-interfaces-with-default-interface-methods"></a>Esercitazione: combinare le funzionalità in durante la creazione di classi mediante interfacce con metodi di interfaccia predefiniti

A partire da C# 8.0 su .NET Core 3.0 è possibile definire un'implementazione quando si dichiara un membro di un'interfaccia. Questa funzionalità fornisce nuove funzionalità in cui è possibile definire le implementazioni predefinite per le funzionalità dichiarate nelle interfacce. Le classi possono scegliere quando eseguire l'override della funzionalità, quando utilizzare la funzionalità predefinita e quando non dichiarare il supporto per le funzionalità discrete.

In questa esercitazione si apprenderà come:

> [!div class="checklist"]
>
> * Creare interfacce con implementazioni che descrivono funzionalità discrete.
> * Creare classi che usano le implementazioni predefinite.
> * Creare classi che eseguono l'override di alcune o di tutte le implementazioni predefinite.

## <a name="prerequisites"></a>Prerequisites

È necessario configurare il computer per l'esecuzione di .NET Core, incluso il C# compilatore 8,0. Il C# compilatore 8,0 è disponibile a partire da [Visual Studio 2019 versione 16,3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)o [.NET Core 3,0 SDK](https://dotnet.microsoft.com/download/dotnet-core) o versione successiva.

## <a name="limitations-of-extension-methods"></a>Limitazioni dei metodi di estensione

Uno dei modi in cui è possibile implementare il comportamento che viene visualizzato come parte di un'interfaccia consiste nel definire [metodi di estensione](../programming-guide/classes-and-structs/extension-methods.md) che forniscono il comportamento predefinito. Le interfacce dichiarano un set minimo di membri, fornendo una superficie di attacco maggiore per qualsiasi classe che implementa tale interfaccia. I metodi di estensione in <xref:System.Linq.Enumerable>, ad esempio, forniscono l'implementazione per qualsiasi sequenza come origine di una query LINQ.

I metodi di estensione vengono risolti in fase di compilazione, usando il tipo dichiarato della variabile. Le classi che implementano l'interfaccia possono fornire un'implementazione migliore per qualsiasi metodo di estensione. Le dichiarazioni di variabili devono corrispondere al tipo di implementazione per consentire al compilatore di scegliere l'implementazione. Quando il tipo in fase di compilazione corrisponde all'interfaccia, le chiamate al metodo vengono risolte nel metodo di estensione. Un altro problema con i metodi di estensione è che questi metodi sono accessibili laddove la classe che contiene i metodi di estensione è accessibile. Le classi non possono dichiarare se devono o non devono fornire funzionalità dichiarate nei metodi di estensione.

A partire C# da 8,0, è possibile dichiarare le implementazioni predefinite come metodi di interfaccia. Quindi, ogni classe utilizza automaticamente l'implementazione predefinita. Qualsiasi classe in grado di fornire un'implementazione migliore può eseguire l'override della definizione del metodo di interfaccia con un algoritmo migliore. In un certo senso, questa tecnica è simile a come si possono usare i [metodi di estensione](../programming-guide/classes-and-structs/extension-methods.md).

In questo articolo si apprenderà come le implementazioni dell'interfaccia predefinite consentano nuovi scenari.

## <a name="design-the-application"></a>Progettare l'applicazione

Si consideri un'applicazione di automazione domestica. Probabilmente si hanno molti tipi diversi di luci e indicatori che possono essere usati in tutta la casa. Ogni luce deve supportare le API per attivarle e disattivarle e per segnalare lo stato corrente. Alcune luci e indicatori possono supportare altre funzionalità, ad esempio:

- Accendere la luce, quindi spegnerla dopo un timer.
- Lampeggiare la luce per un certo periodo di tempo.

Alcune di queste funzionalità estese potrebbero essere emulate in dispositivi che supportano il set minimo. Che indica che fornisce un'implementazione predefinita. Per i dispositivi con più funzionalità integrate, il software del dispositivo utilizzerebbe le funzionalità native. Per altre luci, può scegliere di implementare l'interfaccia e di usare l'implementazione predefinita.

I membri di interfaccia predefiniti sono una soluzione migliore per questo scenario rispetto ai metodi di estensione. Gli autori delle classi possono controllare le interfacce che scelgono di implementare. Le interfacce che scelgono sono disponibili come metodi. Inoltre, poiché i metodi di interfaccia predefiniti sono virtuali per impostazione predefinita, la distribuzione del metodo sceglie sempre l'implementazione nella classe.

Viene ora creato il codice per illustrare queste differenze.

## <a name="create-interfaces"></a>Creare interfacce

Per iniziare, creare l'interfaccia che definisce il comportamento per tutte le luci:

[!code-csharp[Declare base interface](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/UnusedExampleCode.cs?name=SnippetILightInterfaceV1)]

Una fixture di base di overhead può implementare questa interfaccia come illustrato nel codice seguente:

[!code-csharp[First overhead light](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/UnusedExampleCode.cs?name=SnippetOverheadLightV1)]

In questa esercitazione il codice non consente di guidare i dispositivi, ma emula le attività scrivendo messaggi nella console. È possibile esplorare il codice senza automatizzare la propria abitazione.

Definire quindi l'interfaccia per una luce che può essere disattivata automaticamente dopo un timeout:

[!code-csharp[pure Timer interface](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/UnusedExampleCode.cs?name=SnippetPureTimerInterface)]

È possibile aggiungere un'implementazione di base alla luce del sovraccarico, ma una soluzione migliore consiste nel modificare questa definizione di interfaccia per fornire un'implementazione di `virtual` predefinita:

[!code-csharp[Timer interface](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/ITimerLight.cs?name=SnippetTimerLightFinal)]

Con l'aggiunta di questa modifica, la classe `OverheadLight` può implementare la funzione timer dichiarando il supporto per l'interfaccia:

```csharp
public class OverheadLight : ITimerLight { }
```

Un tipo di luce diverso può supportare un protocollo più sofisticato. Può fornire la propria implementazione per `TurnOnFor`, come illustrato nel codice seguente:

[!code-csharp[Override the timer function](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/HalogenLight.cs?name=SnippetHalogenLight)]

A differenza dei metodi della classe virtuale che eseguono l'override, la dichiarazione di `TurnOnFor` nella classe `HalogenLight` non usa la parola chiave `override`.

## <a name="mix-and-match-capabilities"></a>Funzionalità di combinazione e corrispondenza

I vantaggi dei metodi di interfaccia predefiniti diventano più chiari quando si introducono funzionalità più avanzate. L'uso delle interfacce consente di combinare e confrontare le funzionalità. Consente inoltre a ogni autore di classi di scegliere tra l'implementazione predefinita e un'implementazione personalizzata. Aggiungere un'interfaccia con un'implementazione predefinita per una luce lampeggiante:

[!code-csharp[Define the blinking light interface](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/IBlinkingLight.cs?name=SnippetBlinkingLight)]

L'implementazione predefinita consente a qualsiasi luce di lampeggiare. La luce del sovraccarico può aggiungere funzionalità di timer e di lampeggio usando l'implementazione predefinita:

[!code-csharp[Use the default blink function](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/OverheadLight.cs?name=SnippetOverheadLight)]

Un nuovo tipo di luce, il `LEDLight` supporta la funzione timer e la funzione Blink direttamente. Questo stile chiaro implementa le interfacce `ITimerLight` e `IBlinkingLight` ed esegue l'override del metodo `Blink`:

[!code-csharp[Override the blink function](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/LEDLight.cs?name=SnippetLEDLight)]

Una `ExtraFancyLight` potrebbe supportare direttamente le funzioni Blink e timer:

[!code-csharp[Override the blink and timer function](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/ExtraFancyLight.cs?name=SnippetExtraFancyLight)]

Il `HalogenLight` creato in precedenza non supporta il lampeggio. Quindi, non aggiungere la `IBlinkingLight` all'elenco delle interfacce supportate.

## <a name="detect-the-light-types-using-pattern-matching"></a>Rilevare i tipi leggeri usando i criteri di ricerca

Scriviamo quindi un codice di test. È possibile usare la funzionalità C#di ricerca dei [criteri](../pattern-matching.md) di ricerca per determinare le funzionalità di una luce esaminando le interfacce supportate.  Il metodo seguente consente di esercitare le funzionalità supportate di ogni luce:

[!code-csharp[Test a light's capabilities](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/Program.cs?name=SnippetTestLightFunctions)]

Il codice seguente nel metodo `Main` crea ogni tipo di luce in sequenza e testa tale luce:

[!code-csharp[Test a light's capabilities](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/Program.cs?name=SnippetMainMethod)]

## <a name="how-the-compiler-determines-best-implementation"></a>Come il compilatore determina l'implementazione migliore

In questo scenario viene illustrata un'interfaccia di base senza alcuna implementazione. L'aggiunta di un metodo nell'interfaccia `ILight` introduce nuove complessità. Le regole del linguaggio che governano i metodi di interfaccia predefiniti riducono al minimo l'effetto sulle classi concrete che implementano più interfacce derivate. Viene ora migliorata l'interfaccia originale con un nuovo metodo che Mostra come cambia l'utilizzo. Ogni indicatore chiaro può segnalare lo stato di alimentazione come valore enumerato:

[!code-csharp[Enumeration for power status](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/ILight.cs?name=SnippetPowerStatus)]

L'implementazione predefinita presuppone l'alimentazione CA:

[!code-csharp[Report a default power status](~/samples/snippets/csharp/tutorials/mixins-with-interfaces/ILight.cs?name=SnippetILightInterface)]

Queste modifiche vengono compilate in modo corretto, anche se il `ExtraFancyLight` dichiara il supporto per l'interfaccia `ILight` e le interfacce derivate, `ITimerLight` e `IBlinkingLight`. Nell'interfaccia `ILight` è stata dichiarata un'implementazione "più vicina". Qualsiasi classe che dichiara una sostituzione diventerà un'implementazione "più vicina". Sono stati presentati esempi nelle classi precedenti che hanno scavalcato i membri di altre interfacce derivate.

Evitare di eseguire l'override dello stesso metodo in più interfacce derivate. Questa operazione crea una chiamata al metodo ambigua ogni volta che una classe implementa entrambe le interfacce derivate. Il compilatore non può scegliere un metodo migliore, quindi genera un errore. Se, ad esempio, sia la `IBlinkingLight` che la `ITimerLight` implementano un override di `PowerStatus`, è necessario che il `OverheadLight` fornisca un override più specifico. In caso contrario, il compilatore non può scegliere tra le implementazioni nelle due interfacce derivate. In genere è possibile evitare questa situazione mantenendo le definizioni di interfaccia piccole e incentrate su una sola funzionalità. In questo scenario, ogni funzionalità di una luce è la propria interfaccia; più interfacce vengono ereditate solo dalle classi.

Questo esempio illustra uno scenario in cui è possibile definire funzionalità discrete che possono essere combinate nelle classi. Per dichiarare qualsiasi set di funzionalità supportate, dichiarare le interfacce supportate da una classe. L'utilizzo di metodi di interfaccia predefiniti virtuali consente alle classi di utilizzare o definire un'implementazione diversa per uno o tutti i metodi di interfaccia. Questa funzionalità del linguaggio offre nuovi modi per modellare i sistemi reali che si stanno creando. I metodi di interfaccia predefiniti offrono un modo più chiaro per esprimere le classi correlate che possono combinare e associare funzionalità diverse utilizzando implementazioni virtuali di tali funzionalità.
