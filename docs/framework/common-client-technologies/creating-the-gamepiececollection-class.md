---
title: Creazione della classe GamePieceCollection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4b037ee-1201-4a55-b198-0d6532ed6f35
caps.latest.revision: 8
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b74702d71113c3a9dac654971e7d02f97016218b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="creating-the-gamepiececollection-class"></a>Creazione della classe GamePieceCollection
La classe **GamePieceCollection** deriva dalla classe generica List e introduce metodi per che consentono di gestire più facilmente più oggetti **GamePiece**.  
  
## <a name="creating-the-code"></a>Creazione del codice  
 Il costruttore della classe **GamePieceCollection** inizializza il membro privato *capturedIndex*. Questo campo viene usato per tenere traccia delle parti del gioco che hanno attualmente lo stato mouse capture.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]  
  
 I metodi **ProcessInertia** e **Draw** semplificano il codice necessario nei metodi [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) e [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) del gioco tramite l'enumerazione di tutte le parti del gioco nella raccolta e la chiamata del rispettivo metodo per ogni oggetto **GamePiece**.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]  
  
 Durante l'aggiornamento del gioco viene chiamato anche il metodo **UpdateFromMouse**. Consente a una sola parte del gioco di avere lo stato mouse capture, verificando innanzitutto se lo stato corrente, se presente, è ancora attivo. In questo caso, a nessun'altra parte sarà consentito di verificare lo stato capture.  
  
 Se nessuna parte presenta lo stato capture, il metodo **UpdateFromMouse** enumera ogni parte del gioco dall'ultima alla prima e verifica se quella parte segnala uno stato mouse capture. In questo caso, la parte diventa la parte attualmente con lo stato mouse capture e non vengono eseguite altre elaborazioni. Il metodo **UpdateFromMouse** controlla per primo l'ultimo elemento della raccolta in modo che, se due parti sono sovrapposte, quella con l'ordine Z più elevato ottiene lo stato capture. L'ordine Z non è esplicito né può essere modificato. È governato semplicemente dall'ordine in cui le parti del gioco vengono aggiunte alla raccolta.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]  
  
## <a name="see-also"></a>Vedere anche  
 [Modifiche e inerzia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)   
 [Uso delle modifiche e dell'inerzia in un'applicazione XNA](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)   
 [Creazione della classe GamePiece](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)   
 [Creazione della classe Game1](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)   
 [Listati di codice completi](../../../docs/framework/common-client-technologies/full-code-listings.md)

