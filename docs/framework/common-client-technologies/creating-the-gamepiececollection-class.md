---
title: Creazione della classe GamePieceCollection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4b037ee-1201-4a55-b198-0d6532ed6f35
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: b8b53e5890aaebbad2f0a5f0e058182193b11622
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="creating-the-gamepiececollection-class"></a><span data-ttu-id="ce9f8-102">Creazione della classe GamePieceCollection</span><span class="sxs-lookup"><span data-stu-id="ce9f8-102">Creating the GamePieceCollection Class</span></span>
<span data-ttu-id="ce9f8-103">La classe **GamePieceCollection** deriva dalla classe generica List e introduce metodi per che consentono di gestire più facilmente più oggetti **GamePiece**.</span><span class="sxs-lookup"><span data-stu-id="ce9f8-103">The **GamePieceCollection** class derives from the generic List class, and introduces methods to more easily manage multiple **GamePiece** objects.</span></span>  
  
## <a name="creating-the-code"></a><span data-ttu-id="ce9f8-104">Creazione del codice</span><span class="sxs-lookup"><span data-stu-id="ce9f8-104">Creating the Code</span></span>  
 <span data-ttu-id="ce9f8-105">Il costruttore della classe **GamePieceCollection** inizializza il membro privato *capturedIndex*.</span><span class="sxs-lookup"><span data-stu-id="ce9f8-105">The constructor of the **GamePieceCollection** class initializes the private member *capturedIndex*.</span></span> <span data-ttu-id="ce9f8-106">Questo campo viene usato per tenere traccia delle parti del gioco che hanno attualmente lo stato mouse capture.</span><span class="sxs-lookup"><span data-stu-id="ce9f8-106">This field is used to track which of the game pieces currently has the mouse capture.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]  
  
 <span data-ttu-id="ce9f8-107">I metodi **ProcessInertia** e **Draw** semplificano il codice necessario nei metodi [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) e [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) del gioco tramite l'enumerazione di tutte le parti del gioco nella raccolta e la chiamata del rispettivo metodo per ogni oggetto **GamePiece**.</span><span class="sxs-lookup"><span data-stu-id="ce9f8-107">The **ProcessInertia** and the **Draw** methods simplify the code needed in the game [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) and [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) methods by enumerating all of the game pieces in the collection and calling the respective method on each **GamePiece** object.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]  
  
 <span data-ttu-id="ce9f8-108">Durante l'aggiornamento del gioco viene chiamato anche il metodo **UpdateFromMouse**.</span><span class="sxs-lookup"><span data-stu-id="ce9f8-108">The **UpdateFromMouse** method is also called during game update.</span></span> <span data-ttu-id="ce9f8-109">Consente a una sola parte del gioco di avere lo stato mouse capture, verificando innanzitutto se lo stato corrente, se presente, è ancora attivo.</span><span class="sxs-lookup"><span data-stu-id="ce9f8-109">It enables only one game piece to have the mouse capture by first checking to see if the current capture (if any) is still in effect.</span></span> <span data-ttu-id="ce9f8-110">In questo caso, a nessun'altra parte sarà consentito di verificare lo stato capture.</span><span class="sxs-lookup"><span data-stu-id="ce9f8-110">If so, no other piece is allowed to check for capture.</span></span>  
  
 <span data-ttu-id="ce9f8-111">Se nessuna parte presenta lo stato capture, il metodo **UpdateFromMouse** enumera ogni parte del gioco dall'ultima alla prima e verifica se quella parte segnala uno stato mouse capture.</span><span class="sxs-lookup"><span data-stu-id="ce9f8-111">If no piece currently has the capture, the **UpdateFromMouse** method enumerates each game piece from last to first, and checks to see if that piece reports a mouse capture.</span></span> <span data-ttu-id="ce9f8-112">In questo caso, la parte diventa la parte attualmente con lo stato mouse capture e non vengono eseguite altre elaborazioni.</span><span class="sxs-lookup"><span data-stu-id="ce9f8-112">If so, that piece becomes the current captured piece, and no further processing takes place.</span></span> <span data-ttu-id="ce9f8-113">Il metodo **UpdateFromMouse** controlla per primo l'ultimo elemento della raccolta in modo che, se due parti sono sovrapposte, quella con l'ordine Z più elevato ottiene lo stato capture.</span><span class="sxs-lookup"><span data-stu-id="ce9f8-113">The **UpdateFromMouse** method checks the last item in the collection first so that if two pieces are overlapped, the one with the higher Z-order will obtain the capture.</span></span> <span data-ttu-id="ce9f8-114">L'ordine Z non è esplicito né può essere modificato. È governato semplicemente dall'ordine in cui le parti del gioco vengono aggiunte alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="ce9f8-114">Z-order is not explicit nor changeable; it is governed simply by the order in which game pieces are added to the collection.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]  
  
## <a name="see-also"></a><span data-ttu-id="ce9f8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce9f8-115">See Also</span></span>  
 [<span data-ttu-id="ce9f8-116">Modifiche e inerzia</span><span class="sxs-lookup"><span data-stu-id="ce9f8-116">Manipulations and Inertia</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [<span data-ttu-id="ce9f8-117">Uso delle modifiche e dell'inerzia in un'applicazione XNA</span><span class="sxs-lookup"><span data-stu-id="ce9f8-117">Using Manipulations and Inertia in an XNA Application</span></span>](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [<span data-ttu-id="ce9f8-118">Creazione della classe GamePiece</span><span class="sxs-lookup"><span data-stu-id="ce9f8-118">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [<span data-ttu-id="ce9f8-119">Creazione della classe Game1</span><span class="sxs-lookup"><span data-stu-id="ce9f8-119">Creating the Game1 Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
 [<span data-ttu-id="ce9f8-120">Listati di codice completi</span><span class="sxs-lookup"><span data-stu-id="ce9f8-120">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)
