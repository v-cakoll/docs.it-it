---
title: Pubblicare eventi conformi alle linee guida di .NET-Guida per programmatori C#
ms.date: 05/26/2020
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
ms.openlocfilehash: df2f643f867b93b74d04d8fbd673df545c28938e
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84240746"
---
# <a name="how-to-publish-events-that-conform-to-net-guidelines-c-programming-guide"></a><span data-ttu-id="6d253-102">Come pubblicare eventi conformi alle linee guida di .NET (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="6d253-102">How to publish events that conform to .NET Guidelines (C# Programming Guide)</span></span>

<span data-ttu-id="6d253-103">La procedura seguente illustra come aggiungere eventi che seguono il modello .NET standard alle classi e agli struct.</span><span class="sxs-lookup"><span data-stu-id="6d253-103">The following procedure demonstrates how to add events that follow the standard .NET pattern to your classes and structs.</span></span> <span data-ttu-id="6d253-104">Tutti gli eventi della libreria di classi .NET Framework si basano sul delegato <xref:System.EventHandler> che è definito nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="6d253-104">All events in the .NET Framework class library are based on the <xref:System.EventHandler> delegate, which is defined as follows:</span></span>

```csharp
public delegate void EventHandler(object sender, EventArgs e);
```

> [!NOTE]
> <span data-ttu-id="6d253-105">.NET Framework 2,0 introduce una versione generica di questo delegato <xref:System.EventHandler%601> .</span><span class="sxs-lookup"><span data-stu-id="6d253-105">.NET Framework 2.0 introduces a generic version of this delegate, <xref:System.EventHandler%601>.</span></span> <span data-ttu-id="6d253-106">Negli esempi seguenti viene illustrato l'uso di entrambe le versioni.</span><span class="sxs-lookup"><span data-stu-id="6d253-106">The following examples show how to use both versions.</span></span>

<span data-ttu-id="6d253-107">Anche se gli eventi nelle classi definite possono essere basati su qualsiasi tipo di delegato valido, anche delegati che restituiscono un valore, è in genere consigliabile basare gli eventi sul modello .NET tramite <xref:System.EventHandler> , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6d253-107">Although events in classes that you define can be based on any valid delegate type, even delegates that return a value, it is generally recommended that you base your events on the .NET pattern by using <xref:System.EventHandler>, as shown in the following example.</span></span>

<span data-ttu-id="6d253-108">Il nome `EventHandler` può causare un po' di confusione perché non gestisce effettivamente l'evento.</span><span class="sxs-lookup"><span data-stu-id="6d253-108">The name `EventHandler` can lead to a bit of confusion as it doesn't actually handle the event.</span></span> <span data-ttu-id="6d253-109"><xref:System.EventHandler>, E Generic <xref:System.EventHandler%601> sono tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="6d253-109">The <xref:System.EventHandler>, and generic <xref:System.EventHandler%601> are delegate types.</span></span> <span data-ttu-id="6d253-110">Un metodo o un'espressione lambda la cui firma corrisponde alla definizione del delegato è il *gestore eventi* e verrà richiamato quando viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="6d253-110">A method or lambda expression whose signature matches the delegate definition is the *event handler* and will be invoked when the event is raised.</span></span>

## <a name="publish-events-based-on-the-eventhandler-pattern"></a><span data-ttu-id="6d253-111">Pubblicare eventi in base al modello EventHandler</span><span class="sxs-lookup"><span data-stu-id="6d253-111">Publish events based on the EventHandler pattern</span></span>

1. <span data-ttu-id="6d253-112">Ignorare questo passaggio e andare al passaggio 3a se non è necessario inviare dati personalizzati con l'evento. Dichiarare la classe per i dati personalizzati in un ambito visibile per le classi del server di pubblicazione e del Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="6d253-112">(Skip this step and go to Step 3a if you do not have to send custom data with your event.) Declare the class for your custom data at a scope that is visible to both your publisher and subscriber classes.</span></span> <span data-ttu-id="6d253-113">Aggiungere i membri necessari per contenere i dati di evento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6d253-113">Then add the required members to hold your custom event data.</span></span> <span data-ttu-id="6d253-114">In questo esempio viene restituita una semplice stringa.</span><span class="sxs-lookup"><span data-stu-id="6d253-114">In this example, a simple string is returned.</span></span>

    ```csharp
    public class CustomEventArgs : EventArgs
    {
        public CustomEventArgs(string message)
        {
            Message = message;
        }

        public string Message { get; set; }
    }
    ```

2. <span data-ttu-id="6d253-115">Ignorare questo passaggio se si usa la versione generica di <xref:System.EventHandler%601> . Dichiarare un delegato nella classe di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="6d253-115">(Skip this step if you are using the generic version of <xref:System.EventHandler%601>.) Declare a delegate in your publishing class.</span></span> <span data-ttu-id="6d253-116">Assegnargli un nome che termina con `EventHandler` .</span><span class="sxs-lookup"><span data-stu-id="6d253-116">Give it a name that ends with `EventHandler`.</span></span> <span data-ttu-id="6d253-117">Il secondo parametro specifica il `EventArgs` tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6d253-117">The second parameter specifies your custom `EventArgs` type.</span></span>

    ```csharp
    public delegate void CustomEventHandler(object sender, CustomEventArgs args);
    ```

3. <span data-ttu-id="6d253-118">Dichiarare l'evento nella classe di pubblicazione usando uno dei passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="6d253-118">Declare the event in your publishing class by using one of the following steps.</span></span>

    1. <span data-ttu-id="6d253-119">Se non si ha una classe EventArgs personalizzata, il tipo di evento sarà il delegato EventHandler non generico.</span><span class="sxs-lookup"><span data-stu-id="6d253-119">If you have no custom EventArgs class, your Event type will be the non-generic EventHandler delegate.</span></span> <span data-ttu-id="6d253-120">Non è necessario dichiarare il delegato perché è già dichiarato nello spazio dei nomi <xref:System>, incluso quando si crea il progetto C#.</span><span class="sxs-lookup"><span data-stu-id="6d253-120">You do not have to declare the delegate because it is already declared in the <xref:System> namespace that is included when you create your C# project.</span></span> <span data-ttu-id="6d253-121">Aggiungere il codice seguente alla classe dell'editore.</span><span class="sxs-lookup"><span data-stu-id="6d253-121">Add the following code to your publisher class.</span></span>

        ```csharp
        public event EventHandler RaiseCustomEvent;
        ```

    2. <span data-ttu-id="6d253-122">Se si usa la versione non generica di <xref:System.EventHandler> e si ha una classe personalizzata derivata da <xref:System.EventArgs>, dichiarare l'evento all'interno della classe di pubblicazione e usare il delegato del passaggio 2 come tipo.</span><span class="sxs-lookup"><span data-stu-id="6d253-122">If you are using the non-generic version of <xref:System.EventHandler> and you have a custom class derived from <xref:System.EventArgs>, declare your event inside your publishing class and use your delegate from step 2 as the type.</span></span>

        ```csharp
        public event CustomEventHandler RaiseCustomEvent;
        ```

    3. <span data-ttu-id="6d253-123">Se si usa la versione generica, non è necessario un delegato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6d253-123">If you are using the generic version, you do not need a custom delegate.</span></span> <span data-ttu-id="6d253-124">Al contrario, nella classe di pubblicazione specificare il tipo di evento come `EventHandler<CustomEventArgs>`, sostituendo il nome della classe racchiuso tra parentesi acute.</span><span class="sxs-lookup"><span data-stu-id="6d253-124">Instead, in your publishing class, you specify your event type as `EventHandler<CustomEventArgs>`, substituting the name of your own class between the angle brackets.</span></span>

        ```csharp
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;
        ```

## <a name="example"></a><span data-ttu-id="6d253-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d253-125">Example</span></span>

<span data-ttu-id="6d253-126">L'esempio seguente illustra i passaggi precedenti usando una classe EventArgs personalizzata e <xref:System.EventHandler%601> come tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="6d253-126">The following example demonstrates the previous steps by using a custom EventArgs class and <xref:System.EventHandler%601> as the event type.</span></span>

[!code-csharp[csProgGuideEvents#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#2)]

## <a name="see-also"></a><span data-ttu-id="6d253-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d253-127">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="6d253-128">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="6d253-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6d253-129">Events</span><span class="sxs-lookup"><span data-stu-id="6d253-129">Events</span></span>](index.md)
- [<span data-ttu-id="6d253-130">Delegati</span><span class="sxs-lookup"><span data-stu-id="6d253-130">Delegates</span></span>](../delegates/index.md)
