---
title: Come pubblicare gli eventi conformi alle linee guida di .NET Framework - Guida per programmatori C
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
ms.openlocfilehash: 90c079b9f7dbf2a1d963b7eee4447145d7a10432
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167534"
---
# <a name="how-to-publish-events-that-conform-to-net-framework-guidelines-c-programming-guide"></a><span data-ttu-id="33156-102">Come pubblicare gli eventi conformi alle linee guida di .NET Framework (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="33156-102">How to publish events that conform to .NET Framework Guidelines (C# Programming Guide)</span></span>
<span data-ttu-id="33156-103">La procedura seguente illustra come aggiungere eventi che seguono lo schema .NET Framework standard a classi e struct.</span><span class="sxs-lookup"><span data-stu-id="33156-103">The following procedure demonstrates how to add events that follow the standard .NET Framework pattern to your classes and structs.</span></span> <span data-ttu-id="33156-104">Tutti gli eventi della libreria di classi .NET Framework si basano sul delegato <xref:System.EventHandler> che è definito nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="33156-104">All events in the .NET Framework class library are based on the <xref:System.EventHandler> delegate, which is defined as follows:</span></span>  
  
```csharp  
public delegate void EventHandler(object sender, EventArgs e);  
```  
  
> [!NOTE]
> <span data-ttu-id="33156-105">.NET Framework 2.0 introduce una versione generica di questo delegato, <xref:System.EventHandler%601>.</span><span class="sxs-lookup"><span data-stu-id="33156-105">The .NET Framework 2.0 introduces a generic version of this delegate, <xref:System.EventHandler%601>.</span></span> <span data-ttu-id="33156-106">Negli esempi seguenti viene illustrato l'uso di entrambe le versioni.</span><span class="sxs-lookup"><span data-stu-id="33156-106">The following examples show how to use both versions.</span></span>  
  
 <span data-ttu-id="33156-107">Anche se gli eventi nelle classi che vengono definite possono essere basati su qualsiasi tipo di delegato valido, inclusi i delegati che restituiscono un valore, è in genere consigliabile basare gli eventi sullo schema .NET Framework usando <xref:System.EventHandler>, come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="33156-107">Although events in classes that you define can be based on any valid delegate type, even delegates that return a value, it is generally recommended that you base your events on the .NET Framework pattern by using <xref:System.EventHandler>, as shown in the following example.</span></span>  
  
### <a name="to-publish-events-based-on-the-eventhandler-pattern"></a><span data-ttu-id="33156-108">Per pubblicare eventi basati sul modello EventHandler</span><span class="sxs-lookup"><span data-stu-id="33156-108">To publish events based on the EventHandler pattern</span></span>  
  
1. <span data-ttu-id="33156-109">(Salta questo passaggio e vai al passaggio 3a se non devi inviare dati personalizzati con il tuo evento.) Dichiarare la classe per i dati personalizzati in un ambito visibile sia alle classi del server di pubblicazione che a quelle del sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="33156-109">(Skip this step and go to Step 3a if you do not have to send custom data with your event.) Declare the class for your custom data at a scope that is visible to both your publisher and subscriber classes.</span></span> <span data-ttu-id="33156-110">Aggiungere i membri necessari per contenere i dati di evento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="33156-110">Then add the required members to hold your custom event data.</span></span> <span data-ttu-id="33156-111">In questo esempio viene restituita una semplice stringa.</span><span class="sxs-lookup"><span data-stu-id="33156-111">In this example, a simple string is returned.</span></span>  
  
    ```csharp  
    public class CustomEventArgs : EventArgs  
    {  
        public CustomEventArgs(string s)  
        {  
            msg = s;  
        }  
        private string msg;  
        public string Message  
        {  
            get { return msg; }  
        }
    }  
    ```  
  
2. <span data-ttu-id="33156-112">(Saltare questo passaggio se si <xref:System.EventHandler%601> utilizza la versione generica di .) Dichiarare un delegato nella classe di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="33156-112">(Skip this step if you are using the generic version of <xref:System.EventHandler%601> .) Declare a delegate in your publishing class.</span></span> <span data-ttu-id="33156-113">Assegnargli un nome che termini con *EventHandler*.</span><span class="sxs-lookup"><span data-stu-id="33156-113">Give it a name that ends with *EventHandler*.</span></span> <span data-ttu-id="33156-114">Il secondo parametro specifica il tipo EventArgs personalizzato.</span><span class="sxs-lookup"><span data-stu-id="33156-114">The second parameter specifies your custom EventArgs type.</span></span>  
  
    ```csharp  
    public delegate void CustomEventHandler(object sender, CustomEventArgs a);  
    ```  
  
3. <span data-ttu-id="33156-115">Dichiarare l'evento nella classe di pubblicazione usando uno dei passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="33156-115">Declare the event in your publishing class by using one of the following steps.</span></span>  
  
    1. <span data-ttu-id="33156-116">Se non si ha una classe EventArgs personalizzata, il tipo di evento sarà il delegato EventHandler non generico.</span><span class="sxs-lookup"><span data-stu-id="33156-116">If you have no custom EventArgs class, your Event type will be the non-generic EventHandler delegate.</span></span> <span data-ttu-id="33156-117">Non è necessario dichiarare il delegato perché è già dichiarato nello spazio dei nomi <xref:System>, incluso quando si crea il progetto C#.</span><span class="sxs-lookup"><span data-stu-id="33156-117">You do not have to declare the delegate because it is already declared in the <xref:System> namespace that is included when you create your C# project.</span></span> <span data-ttu-id="33156-118">Aggiungere il codice seguente alla classe dell'editore.</span><span class="sxs-lookup"><span data-stu-id="33156-118">Add the following code to your publisher class.</span></span>  
  
        ```csharp  
        public event EventHandler RaiseCustomEvent;  
        ```  
  
    2. <span data-ttu-id="33156-119">Se si usa la versione non generica di <xref:System.EventHandler> e si ha una classe personalizzata derivata da <xref:System.EventArgs>, dichiarare l'evento all'interno della classe di pubblicazione e usare il delegato del passaggio 2 come tipo.</span><span class="sxs-lookup"><span data-stu-id="33156-119">If you are using the non-generic version of <xref:System.EventHandler> and you have a custom class derived from <xref:System.EventArgs>, declare your event inside your publishing class and use your delegate from step 2 as the type.</span></span>  
  
        ```csharp  
        public event CustomEventHandler RaiseCustomEvent;  
        ```  
  
    3. <span data-ttu-id="33156-120">Se si usa la versione generica, non è necessario un delegato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="33156-120">If you are using the generic version, you do not need a custom delegate.</span></span> <span data-ttu-id="33156-121">Al contrario, nella classe di pubblicazione specificare il tipo di evento come `EventHandler<CustomEventArgs>`, sostituendo il nome della classe racchiuso tra parentesi acute.</span><span class="sxs-lookup"><span data-stu-id="33156-121">Instead, in your publishing class, you specify your event type as `EventHandler<CustomEventArgs>`, substituting the name of your own class between the angle brackets.</span></span>  
  
        ```csharp  
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;  
        ```  
  
## <a name="example"></a><span data-ttu-id="33156-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="33156-122">Example</span></span>  
 <span data-ttu-id="33156-123">L'esempio seguente illustra i passaggi precedenti usando una classe EventArgs personalizzata e <xref:System.EventHandler%601> come tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="33156-123">The following example demonstrates the previous steps by using a custom EventArgs class and <xref:System.EventHandler%601> as the event type.</span></span>  
  
 [!code-csharp[csProgGuideEvents#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="33156-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33156-124">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="33156-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="33156-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="33156-126">Events</span><span class="sxs-lookup"><span data-stu-id="33156-126">Events</span></span>](./index.md)
- [<span data-ttu-id="33156-127">Delegati</span><span class="sxs-lookup"><span data-stu-id="33156-127">Delegates</span></span>](../delegates/index.md)
