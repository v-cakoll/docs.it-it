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
# <a name="how-to-publish-events-that-conform-to-net-guidelines-c-programming-guide"></a>Come pubblicare eventi conformi alle linee guida di .NET (Guida per programmatori C#)

La procedura seguente illustra come aggiungere eventi che seguono il modello .NET standard alle classi e agli struct. Tutti gli eventi della libreria di classi .NET Framework si basano sul delegato <xref:System.EventHandler> che è definito nel modo seguente:

```csharp
public delegate void EventHandler(object sender, EventArgs e);
```

> [!NOTE]
> .NET Framework 2,0 introduce una versione generica di questo delegato <xref:System.EventHandler%601> . Negli esempi seguenti viene illustrato l'uso di entrambe le versioni.

Anche se gli eventi nelle classi definite possono essere basati su qualsiasi tipo di delegato valido, anche delegati che restituiscono un valore, è in genere consigliabile basare gli eventi sul modello .NET tramite <xref:System.EventHandler> , come illustrato nell'esempio seguente.

Il nome `EventHandler` può causare un po' di confusione perché non gestisce effettivamente l'evento. <xref:System.EventHandler>, E Generic <xref:System.EventHandler%601> sono tipi delegati. Un metodo o un'espressione lambda la cui firma corrisponde alla definizione del delegato è il *gestore eventi* e verrà richiamato quando viene generato l'evento.

## <a name="publish-events-based-on-the-eventhandler-pattern"></a>Pubblicare eventi in base al modello EventHandler

1. Ignorare questo passaggio e andare al passaggio 3a se non è necessario inviare dati personalizzati con l'evento. Dichiarare la classe per i dati personalizzati in un ambito visibile per le classi del server di pubblicazione e del Sottoscrittore. Aggiungere i membri necessari per contenere i dati di evento personalizzati. In questo esempio viene restituita una semplice stringa.

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

2. Ignorare questo passaggio se si usa la versione generica di <xref:System.EventHandler%601> . Dichiarare un delegato nella classe di pubblicazione. Assegnargli un nome che termina con `EventHandler` . Il secondo parametro specifica il `EventArgs` tipo personalizzato.

    ```csharp
    public delegate void CustomEventHandler(object sender, CustomEventArgs args);
    ```

3. Dichiarare l'evento nella classe di pubblicazione usando uno dei passaggi seguenti.

    1. Se non si ha una classe EventArgs personalizzata, il tipo di evento sarà il delegato EventHandler non generico. Non è necessario dichiarare il delegato perché è già dichiarato nello spazio dei nomi <xref:System>, incluso quando si crea il progetto C#. Aggiungere il codice seguente alla classe dell'editore.

        ```csharp
        public event EventHandler RaiseCustomEvent;
        ```

    2. Se si usa la versione non generica di <xref:System.EventHandler> e si ha una classe personalizzata derivata da <xref:System.EventArgs>, dichiarare l'evento all'interno della classe di pubblicazione e usare il delegato del passaggio 2 come tipo.

        ```csharp
        public event CustomEventHandler RaiseCustomEvent;
        ```

    3. Se si usa la versione generica, non è necessario un delegato personalizzato. Al contrario, nella classe di pubblicazione specificare il tipo di evento come `EventHandler<CustomEventArgs>`, sostituendo il nome della classe racchiuso tra parentesi acute.

        ```csharp
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;
        ```

## <a name="example"></a>Esempio

L'esempio seguente illustra i passaggi precedenti usando una classe EventArgs personalizzata e <xref:System.EventHandler%601> come tipo di evento.

[!code-csharp[csProgGuideEvents#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#2)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Delegate>
- [Guida per programmatori C#](../index.md)
- [Events](index.md)
- [Delegati](../delegates/index.md)
