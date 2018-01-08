---
title: Creazione della classe Game1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47932ce3-2ba5-476f-a26b-3ddfd5226f27
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7453c4f650e2dcadd3b8fac27b66f4db97fa0136
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="creating-the-game1-class"></a><span data-ttu-id="896f2-102">Creazione della classe Game1</span><span class="sxs-lookup"><span data-stu-id="896f2-102">Creating the Game1 Class</span></span>
<span data-ttu-id="896f2-103">Come per tutti i progetti di Microsoft XNA, la classe Game1 deriva dalla classe [Microsoft.Xna.Framework.Game](http://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx), che fornisce l'inizializzazione dei dispositivi grafici di base, la logica del gioco e il codice di rendering per i giochi XNA.</span><span class="sxs-lookup"><span data-stu-id="896f2-103">As with all Microsoft XNA projects, the Game1 class derives from the [Microsoft.Xna.Framework.Game](http://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx) class, which provides basic graphics device initialization, game logic, and rendering code for XNA games.</span></span> <span data-ttu-id="896f2-104">La classe Game1 è alquanto semplice perché la maggior parte del lavoro spetta alle classi GamePiece e GamePieceCollection.</span><span class="sxs-lookup"><span data-stu-id="896f2-104">The Game1 class is fairly simple because most of the work in done in the GamePiece and GamePieceCollection classes.</span></span>  
  
## <a name="creating-the-code"></a><span data-ttu-id="896f2-105">Creazione del codice</span><span class="sxs-lookup"><span data-stu-id="896f2-105">Creating the Code</span></span>  
 <span data-ttu-id="896f2-106">I membri privati per la classe sono costituiti da un oggetto **GamePieceCollection** che include le parti del gioco, da un oggetto [GraphicsDeviceManager](http://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) e da un oggetto [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) usato per il rendering delle parti del gioco.</span><span class="sxs-lookup"><span data-stu-id="896f2-106">The private members for the class consist of a **GamePieceCollection** object to hold the game pieces, a [GraphicsDeviceManager](http://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) object, and a [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) object used to render game pieces.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_privatemembers)]  
  
 <span data-ttu-id="896f2-107">Durante l'inizializzazione del gioco, viene creata un'istanza di questi oggetti.</span><span class="sxs-lookup"><span data-stu-id="896f2-107">During game initialization, these objects are instantiated.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_ConstructorInitialize](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_constructorinitialize)]  
  
 <span data-ttu-id="896f2-108">Quando viene chiamato il metodo [LoadContent](http://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx), vengono create le parti del gioco che verranno assegnate all'oggetto **GamePieceCollection**.</span><span class="sxs-lookup"><span data-stu-id="896f2-108">When the [LoadContent](http://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx) method is called, the game pieces are created and assigned to the **GamePieceCollection** object.</span></span> <span data-ttu-id="896f2-109">Sono disponibili due tipi di parti del gioco.</span><span class="sxs-lookup"><span data-stu-id="896f2-109">There are two types of game pieces.</span></span> <span data-ttu-id="896f2-110">Il fattore di scala per le parti viene modificato leggermente in modo che siano disponibili alcune parti più piccole e altre più grandi.</span><span class="sxs-lookup"><span data-stu-id="896f2-110">The scale factor for the pieces is changed slightly so that there are some smaller and some larger pieces.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_LoadContent](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_loadcontent)]  
  
 <span data-ttu-id="896f2-111">Il metodo [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) viene chiamato ripetutamente da XNA Framework durante l'esecuzione del gioco.</span><span class="sxs-lookup"><span data-stu-id="896f2-111">The [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) method is called repeatedly by the XNA Framework while the game is running.</span></span> <span data-ttu-id="896f2-112">Il metodo [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) chiama i metodi **ProcessInertia** e **UpdateFromMouse** nella raccolta di parti del gioco.</span><span class="sxs-lookup"><span data-stu-id="896f2-112">The [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) method calls the **ProcessInertia** and the **UpdateFromMouse** methods on the game piece collection.</span></span> <span data-ttu-id="896f2-113">Questi metodi sono descritti in [Creazione della classe GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span><span class="sxs-lookup"><span data-stu-id="896f2-113">These methods are described in [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_UpdateGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_updategame)]  
  
 <span data-ttu-id="896f2-114">Anche il metodo [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) viene chiamato ripetutamente da XNA Framework mentre il gioco è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="896f2-114">The [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) method is also called repeatedly by the XNA Framework while the game is running.</span></span> <span data-ttu-id="896f2-115">Il metodo [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) esegue il rendering delle parti del gioco chiamando il metodo **Draw** dell'oggetto **GamePieceCollection**.</span><span class="sxs-lookup"><span data-stu-id="896f2-115">The [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) method performs the rendering of game pieces by calling the **Draw** method of the **GamePieceCollection** object.</span></span> <span data-ttu-id="896f2-116">Questo metodo viene descritto in [Creazione della classe GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span><span class="sxs-lookup"><span data-stu-id="896f2-116">This method is described in[Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_DrawGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_drawgame)]  
  
## <a name="see-also"></a><span data-ttu-id="896f2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="896f2-117">See Also</span></span>  
 [<span data-ttu-id="896f2-118">Modifiche e inerzia</span><span class="sxs-lookup"><span data-stu-id="896f2-118">Manipulations and Inertia</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [<span data-ttu-id="896f2-119">Uso delle modifiche e dell'inerzia in un'applicazione XNA</span><span class="sxs-lookup"><span data-stu-id="896f2-119">Using Manipulations and Inertia in an XNA Application</span></span>](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [<span data-ttu-id="896f2-120">Creazione della classe GamePiece</span><span class="sxs-lookup"><span data-stu-id="896f2-120">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [<span data-ttu-id="896f2-121">Creazione della classe GamePieceCollection</span><span class="sxs-lookup"><span data-stu-id="896f2-121">Creating the GamePieceCollection Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
 [<span data-ttu-id="896f2-122">Listati di codice completi</span><span class="sxs-lookup"><span data-stu-id="896f2-122">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)
