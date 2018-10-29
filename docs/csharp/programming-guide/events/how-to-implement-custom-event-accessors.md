---
title: 'Procedura: implementare funzioni di accesso a eventi personalizzati (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: 759a7a4518a371449723a23669816bbc0fbc0dee
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836709"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a>Procedura: implementare funzioni di accesso a eventi personalizzati (Guida per programmatori C#)
Un evento è un tipo speciale di delegato multicast che può essere richiamato solo dall'interno della classe in cui è dichiarato. Il codice client sottoscrive l'evento fornendo un riferimento a un metodo che deve essere richiamato quando l'evento viene generato. Questi metodi vengono aggiunti all'elenco di chiamate del delegato tramite funzioni di accesso agli eventi, che sono simili alle funzioni di accesso alle proprietà, ad eccezione del fatto che sono denominate `add` e `remove`. Nella maggior parte dei casi, non è necessario fornire funzioni di accesso agli eventi personalizzate. Se nel codice non vengono fornite funzioni di accesso agli eventi personalizzate, il compilatore le aggiunge automaticamente. In alcuni casi tuttavia può essere necessario fornire un comportamento personalizzato. Uno di questi casi è illustrato nell'argomento [Procedura: Implementare gli eventi di interfaccia ](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra come implementare le funzioni di accesso agli eventi add e remove personalizzate. Anche se è possibile sostituire qualsiasi parte di codice nelle funzioni di accesso, si consiglia di bloccare l'evento prima di aggiungere o rimuovere un nuovo metodo del gestore eventi.  
  
[!code-csharp[IDrawingObject.OnDraw](codesnippet/CSharp/how-to-implement-interface-events_1.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a>Vedere anche

- [Eventi](../../../csharp/programming-guide/events/index.md)  
- [event](../../../csharp/language-reference/keywords/event.md)