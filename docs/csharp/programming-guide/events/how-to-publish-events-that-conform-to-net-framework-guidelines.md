---
title: 'Procedura: pubblicare eventi conformi alle linee guida di .NET Framework (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 570729e432146b4ef97e4c487f644b12b354bb4a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-publish-events-that-conform-to-net-framework-guidelines-c-programming-guide"></a>Procedura: pubblicare eventi conformi alle linee guida di .NET Framework (Guida per programmatori C#)
La procedura seguente illustra come aggiungere a classi e struct gli eventi che seguono il modello standard [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Tutti gli eventi della libreria di classi [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] si basano sul delegato <xref:System.EventHandler>, che viene definito come segue:  
  
```csharp  
public delegate void EventHandler(object sender, EventArgs e);  
```  
  
> [!NOTE]
>  [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] introduce una versione generica di questo delegato, <xref:System.EventHandler%601>. Negli esempi seguenti viene illustrato l'uso di entrambe le versioni.  
  
 Anche se gli eventi nelle classi che vengono definite possono essere basati su qualsiasi tipo di delegato valido, inclusi i delegati che restituiscono un valore, è in genere consigliabile basare gli eventi sullo schema [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] usando <xref:System.EventHandler>, come illustrato nell'esempio seguente.  
  
### <a name="to-publish-events-based-on-the-eventhandler-pattern"></a>Per pubblicare eventi basati sul modello EventHandler  
  
1.  Ignorare questo passaggio e andare al passaggio 3a se non è necessario inviare i dati personalizzati con l'evento. Dichiarare la classe per i dati personalizzati in un ambito che sia visibile sia per la classe dell'editore che per quella del sottoscrittore. Aggiungere i membri necessari per contenere i dati di evento personalizzati. In questo esempio viene restituita una semplice stringa.  
  
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
  
2.  Ignorare questo passaggio se si sta usando la versione generica di <xref:System.EventHandler%601>. Dichiarare un delegato nella classe di pubblicazione. Assegnargli un nome che termini con *EventHandler*. Il secondo parametro specifica il tipo EventArgs personalizzato.  
  
    ```csharp  
    public delegate void CustomEventHandler(object sender, CustomEventArgs a);  
    ```  
  
3.  Dichiarare l'evento nella classe di pubblicazione usando uno dei passaggi seguenti.  
  
    1.  Se non si ha una classe EventArgs personalizzata, il tipo di evento sarà il delegato EventHandler non generico. Non è necessario dichiarare il delegato perché è già dichiarato nello spazio dei nomi <xref:System>, incluso quando si crea il progetto C#. Aggiungere il codice seguente alla classe dell'editore.  
  
        ```csharp  
        public event EventHandler RaiseCustomEvent;  
        ```  
  
    2.  Se si usa la versione non generica di <xref:System.EventHandler> e si ha una classe personalizzata derivata da <xref:System.EventArgs>, dichiarare l'evento all'interno della classe di pubblicazione e usare il delegato del passaggio 2 come tipo.  
  
        ```csharp  
        public event CustomEventHandler RaiseCustomEvent;  
        ```  
  
    3.  Se si usa la versione generica, non è necessario un delegato personalizzato. Al contrario, nella classe di pubblicazione specificare il tipo di evento come `EventHandler<CustomEventArgs>`, sostituendo il nome della classe racchiuso tra parentesi acute.  
  
        ```csharp  
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;  
        ```  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra i passaggi precedenti usando una classe EventArgs personalizzata e <xref:System.EventHandler%601> come tipo di evento.  
  
 [!code-csharp[csProgGuideEvents#2](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-publish-events-that-conform-to-net-framework-guidelines_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Delegate>  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Eventi](../../../csharp/programming-guide/events/index.md)  
 [Delegati](../../../csharp/programming-guide/delegates/index.md)
