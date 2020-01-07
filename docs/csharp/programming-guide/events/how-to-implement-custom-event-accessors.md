---
title: Come implementare funzioni di accesso agli eventi personalizzati C# -Guida alla programmazione
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: af44b88ddd0e34f9dfd0b56718b5bc7241ef5d03
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635457"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a>Come implementare funzioni di accesso agli eventi personalizzateC# (Guida per programmatori)
Un evento è un tipo speciale di delegato multicast che può essere richiamato solo dall'interno della classe in cui è dichiarato. Il codice client sottoscrive l'evento fornendo un riferimento a un metodo che deve essere richiamato quando l'evento viene generato. Questi metodi vengono aggiunti all'elenco di chiamate del delegato tramite funzioni di accesso agli eventi, che sono simili alle funzioni di accesso alle proprietà, ad eccezione del fatto che sono denominate `add` e `remove`. Nella maggior parte dei casi, non è necessario fornire funzioni di accesso agli eventi personalizzate. Se nel codice non vengono fornite funzioni di accesso agli eventi personalizzate, il compilatore le aggiunge automaticamente. In alcuni casi tuttavia può essere necessario fornire un comportamento personalizzato. Uno di questi casi viene illustrato nell'argomento [come implementare gli eventi di interfaccia](./how-to-implement-interface-events.md).
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra come implementare le funzioni di accesso agli eventi add e remove personalizzate. Anche se è possibile sostituire qualsiasi parte di codice nelle funzioni di accesso, si consiglia di bloccare l'evento prima di aggiungere o rimuovere un nuovo metodo del gestore eventi.  
  
[!code-csharp[IDrawingObject.OnDraw](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a>Vedere anche

- [Eventi](./index.md)
- [event](../../language-reference/keywords/event.md)
