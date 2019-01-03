---
title: Eventi - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 55fe0e8f94d9b350305b634cabb90011e173b572
ms.sourcegitcommit: 882a2f56bf6afdcb40d468e4ae9371296822b68c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2018
ms.locfileid: "53451144"
---
# <a name="events-c-programming-guide"></a>Eventi (Guida per programmatori C#)
Tramite gli eventi, una [classe](../../../csharp/language-reference/keywords/class.md) o un oggetto è in grado di segnalare ad altre classi o oggetti una situazione di interesse. La classe che invia (o *genera*) l'evento è chiamata *autore* e le classi che ricevono (o *gestiscono*) l'evento sono chiamate *sottoscrittori*.  
  
 In un'applicazione C# Web o Windows Form tipica si sottoscrivono eventi generati da controlli quali pulsanti e caselle di riepilogo. È possibile usare l'ambiente di sviluppo integrato (IDE) di Visual C# per cercare gli eventi pubblicati da un controllo e selezionare quelli che si vuole gestire. L'IDE consente di aggiungere automaticamente un metodo vuoto del gestore eventi e il codice per sottoscrivere l'evento. Per altre informazioni, vedere [Procedura: Eseguire e annullare la sottoscrizione a eventi](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  
  
## <a name="events-overview"></a>Cenni preliminari sugli eventi  
 Di seguito sono riportate le proprietà degli eventi:  
  
-   L'autore determina quando viene generato un evento. I sottoscrittori determinano quale azione viene eseguita in risposta all'evento.  
  
-   Un evento può avere più sottoscrittori. Un sottoscrittore può gestire più eventi da più autori.  
  
-   Gli eventi che non hanno sottoscrittore non vengono mai generati.  
  
-   Gli eventi vengono in genere usati per segnalare azioni dell'utente, ad esempio la scelta di un pulsante o di una voce di menu nell'interfaccia utente grafica.  
  
-   Quando un evento ha più sottoscrittori, i gestori eventi vengono richiamati in modo sincrono al momento della generazione dell'evento. Per richiamare gli eventi in modo asincrono, vedere [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).  
  
-   Nella libreria di classi di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] gli eventi sono basati sul delegato <xref:System.EventHandler> e sulla classe di base <xref:System.EventArgs> .  
  
## <a name="related-sections"></a>Sezioni correlate  
 Per altre informazioni, vedere:  
  
-   [Procedura: Eseguire e annullare la sottoscrizione a eventi](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [Procedura: Pubblicare eventi conformi alle linee guida di .NET Framework](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [Procedura: Generare eventi di classe base nelle classi derivate](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [Procedura:  Implementare eventi di interfaccia](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [Procedura: Usare un dizionario per archiviare istanze di evento](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [Procedura: Implementare funzioni di accesso a eventi personalizzati](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  

Per altre informazioni, vedere [Eventi](~/_csharplang/spec/classes.md#events) nella [Specifica del linguaggio C#](../../language-reference/language-specification/index.md). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.
  
## <a name="featured-book-chapters"></a>Capitoli del libro rappresentati  
 [Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegati, eventi ed espressioni Lambda) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29) (Tutto su C# 3.0, terza edizione: più di 250 soluzioni per i programmatori C# 3.0)  
  
 [Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) (Delegati ed eventi) in [Learning C# 3.0: Master the Fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29) (Imparare C# 3.0: concetti di base di C# 3.0)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.EventHandler>  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Delegati](../../../csharp/programming-guide/delegates/index.md)  
- [Creazione di gestori eventi in Windows Form](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
