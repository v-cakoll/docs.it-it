---
title: Eventi - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 183f53a579bdd9f70deb16ca9157c377fa3aff3f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75712312"
---
# <a name="events-c-programming-guide"></a>Eventi (Guida per programmatori C#)
Tramite gli eventi, una [classe](../../language-reference/keywords/class.md) o un oggetto è in grado di segnalare ad altre classi o oggetti una situazione di interesse. La classe che invia (o *genera)* l'evento viene chiamato *editore* e le classi che ricevono (o *gestiscono*) l'evento sono chiamate *sottoscrittori*.  
  
In un'applicazione C# Web o Windows Form tipica si sottoscrivono eventi generati da controlli quali pulsanti e caselle di riepilogo. È possibile usare l'ambiente di sviluppo integrato (IDE) di Visual C# per cercare gli eventi pubblicati da un controllo e selezionare quelli che si vuole gestire. L'IDE consente di aggiungere automaticamente un metodo vuoto del gestore eventi e il codice per sottoscrivere l'evento. Per ulteriori informazioni, vedere [Come sottoscrivere e annullare la sottoscrizione agli eventi](./how-to-subscribe-to-and-unsubscribe-from-events.md).
  
## <a name="events-overview"></a>Cenni preliminari sugli eventi  
 Di seguito sono riportate le proprietà degli eventi:  
  
- L'autore determina quando viene generato un evento. I sottoscrittori determinano quale azione viene eseguita in risposta all'evento.  
  
- Un evento può avere più sottoscrittori. Un sottoscrittore può gestire più eventi da più autori.  
  
- Gli eventi che non hanno sottoscrittore non vengono mai generati.  
  
- Gli eventi vengono in genere usati per segnalare azioni dell'utente, ad esempio la scelta di un pulsante o di una voce di menu nell'interfaccia utente grafica.  
  
- Quando un evento ha più sottoscrittori, i gestori eventi vengono richiamati in modo sincrono al momento della generazione dell'evento. Per richiamare gli eventi in modo asincrono, vedere [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).  
  
- Nella libreria di classi .NET Framework gli eventi sono basati sul delegato <xref:System.EventHandler> e sulla classe di base <xref:System.EventArgs>.  
  
## <a name="related-sections"></a>Sezioni correlate  
 Per altre informazioni, vedere:  
  
- [Come eseguire e annullare la sottoscrizione a eventi](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [Come pubblicare eventi conformi alle linee guida di .NET Framework](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [Come generare eventi di classe base nelle classi derivate](./how-to-raise-base-class-events-in-derived-classes.md)

- [Come implementare eventi di interfaccia](./how-to-implement-interface-events.md)

- [Come implementare funzioni di accesso a eventi personalizzati](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a>Specifiche del linguaggio C#  

Per altre informazioni, vedere [Eventi](~/_csharplang/spec/classes.md#events) nella [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.
  
## <a name="featured-book-chapters"></a>Capitoli del libro rappresentati  
 [Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegati, eventi ed espressioni lambda) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)  
  
 [Delegati ed eventi](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) (Delegati, eventi ed espressioni lambda) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.EventHandler>
- [Guida per programmatori C#](../index.md)
- [Delegati](../delegates/index.md)
- [Creazione di gestori eventi in Windows Forms](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
