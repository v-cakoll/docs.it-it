---
title: Utilizzo delle modifiche e dell'inerzia in un'applicazione XNA
ms.date: 03/30/2017
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
ms.openlocfilehash: 70b8d0c5c098089b6f16ef817ff86698f68cf7c3
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44248904"
---
# <a name="using-manipulations-and-inertia-in-an-xna-application"></a><span data-ttu-id="e81f3-102">Utilizzo delle modifiche e dell'inerzia in un'applicazione XNA</span><span class="sxs-lookup"><span data-stu-id="e81f3-102">Using Manipulations and Inertia in an XNA Application</span></span>
<span data-ttu-id="e81f3-103">Questo articolo descrive come è possibile usare l'elaborazione basata sulle modifiche e sull'inerzia in un'applicazione Microsoft XNA per controllare il movimento delle parti del gioco.</span><span class="sxs-lookup"><span data-stu-id="e81f3-103">This article describes how you can use manipulations and inertia processing in a Microsoft XNA application to control the movement of game pieces.</span></span> <span data-ttu-id="e81f3-104">Prima di leggere questo articolo, è necessario conoscere l'argomento [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) (Panoramica delle modifiche e dell'inerzia) e i concetti di programmazione XNA di base.</span><span class="sxs-lookup"><span data-stu-id="e81f3-104">Before you read this article, you should be familiar with the [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) topic, and be familiar with basic XNA programming concepts.</span></span>  
  
 <span data-ttu-id="e81f3-105">Per eseguire le attività descritte in questo articolo, il progetto XNA deve fare riferimento all'assembly <xref:System.Windows.Input.Manipulations> e [XNA Game Studio](https://msdn.microsoft.com/library/bb200104.aspx) ([download](https://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)) deve essere installato nel computer per consentire al progetto di fare riferimento agli assembly XNA.</span><span class="sxs-lookup"><span data-stu-id="e81f3-105">To perform the tasks described in this article, your XNA project must reference the <xref:System.Windows.Input.Manipulations> assembly, and you must have [XNA Game Studio](https://msdn.microsoft.com/library/bb200104.aspx) ([download](https://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)) installed on your computer so that your project can reference the XNA assemblies.</span></span>  
  
## <a name="overview-of-functionality"></a><span data-ttu-id="e81f3-106">Panoramica delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="e81f3-106">Overview of Functionality</span></span>  
 <span data-ttu-id="e81f3-107">Questo articolo mostra come creare una classe personalizzata che rappresenta una parte del gioco che usa l'elaborazione basata sull'inerzia e sulle modifiche.</span><span class="sxs-lookup"><span data-stu-id="e81f3-107">This article shows you how to create a custom class that represents a game piece that uses manipulation and inertia processing.</span></span> <span data-ttu-id="e81f3-108">Questa classe consente di modificare una parte del gioco sullo schermo trascinandola con il mouse e quindi rilasciandola.</span><span class="sxs-lookup"><span data-stu-id="e81f3-108">This class enables you to manipulate a game piece across the screen by dragging it with the mouse, and then releasing it.</span></span> <span data-ttu-id="e81f3-109">Una volta rilasciata, l'elaborazione basata sull'inerzia fa muovere la parte del gioco come se stesse rallentando gradualmente.</span><span class="sxs-lookup"><span data-stu-id="e81f3-109">Once released, inertia processing keeps the game piece moving as it gradually slows down.</span></span> <span data-ttu-id="e81f3-110">Il movimento è sia lineare che angolare.</span><span class="sxs-lookup"><span data-stu-id="e81f3-110">Movement is both linear and angular.</span></span>  
  
 <span data-ttu-id="e81f3-111">![Semplice applicazione di modifiche e inerzia.](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")</span><span class="sxs-lookup"><span data-stu-id="e81f3-111">![A simple manipulations and inertia application.](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")</span></span>  
  
 <span data-ttu-id="e81f3-112">Inoltre, viene creata una raccolta personalizzata che gestisce più parti del gioco.</span><span class="sxs-lookup"><span data-stu-id="e81f3-112">In addition, a custom collection is created that manages multiple game pieces.</span></span> <span data-ttu-id="e81f3-113">Ciò semplifica la gestione richiesta dalla classe XNA Game.</span><span class="sxs-lookup"><span data-stu-id="e81f3-113">This simplifies the handling that is required from the XNA Game class.</span></span>  
  
 [<span data-ttu-id="e81f3-114">Creazione della classe GamePiece</span><span class="sxs-lookup"><span data-stu-id="e81f3-114">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [<span data-ttu-id="e81f3-115">Creazione della classe GamePieceCollection</span><span class="sxs-lookup"><span data-stu-id="e81f3-115">Creating the GamePieceCollection Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [<span data-ttu-id="e81f3-116">Creazione della classe Game1</span><span class="sxs-lookup"><span data-stu-id="e81f3-116">Creating the Game1 Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [<span data-ttu-id="e81f3-117">Listati di codice completi</span><span class="sxs-lookup"><span data-stu-id="e81f3-117">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## <a name="see-also"></a><span data-ttu-id="e81f3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e81f3-118">See Also</span></span>  
 <xref:System.Windows.Input.Manipulations>  
 [<span data-ttu-id="e81f3-119">Informazioni generali sulle modifiche e sull'inerzia</span><span class="sxs-lookup"><span data-stu-id="e81f3-119">Manipulations and Inertia Overview</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)
