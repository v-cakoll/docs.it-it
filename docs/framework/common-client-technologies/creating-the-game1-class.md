---
title: Creazione della classe Game1
ms.date: 03/30/2017
ms.assetid: 47932ce3-2ba5-476f-a26b-3ddfd5226f27
ms.openlocfilehash: c96fa846d11947af03faec26dd6de99e0aeec052
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452797"
---
# <a name="creating-the-game1-class"></a>Creazione della classe Game1
Come per tutti i progetti di Microsoft XNA, la classe Game1 deriva dalla classe [Microsoft.Xna.Framework.Game](https://docs.microsoft.com/previous-versions/windows/xna/bb197040%28v%3dxnagamestudio.41%29), che fornisce l'inizializzazione dei dispositivi grafici di base, la logica del gioco e il codice di rendering per i giochi XNA. La classe Game1 è alquanto semplice perché la maggior parte del lavoro spetta alle classi GamePiece e GamePieceCollection.  
  
## <a name="creating-the-code"></a>Creazione del codice  
 I membri privati per la classe sono costituiti da un oggetto **GamePieceCollection** che include le parti del gioco, da un oggetto [GraphicsDeviceManager](https://docs.microsoft.com/previous-versions/windows/xna/bb197317%28v%3dxnagamestudio.41%29) e da un oggetto [SpriteBatch](https://docs.microsoft.com/previous-versions/windows/xna/bb199034%28v%3dxnagamestudio.41%29) usato per il rendering delle parti del gioco.  
  
 [!code-csharp[ManipulationXNA#_Game1_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_privatemembers)]  
  
 Durante l'inizializzazione del gioco, viene creata un'istanza di questi oggetti.  
  
 [!code-csharp[ManipulationXNA#_Game1_ConstructorInitialize](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_constructorinitialize)]  
  
 Quando viene chiamato il metodo [LoadContent](https://docs.microsoft.com/previous-versions/windows/xna/bb975766%28v%3dxnagamestudio.41%29), vengono create le parti del gioco che verranno assegnate all'oggetto **GamePieceCollection**. Sono disponibili due tipi di parti del gioco. Il fattore di scala per le parti viene modificato leggermente in modo che siano disponibili alcune parti più piccole e altre più grandi.  
  
 [!code-csharp[ManipulationXNA#_Game1_LoadContent](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_loadcontent)]  
  
 Il metodo [Update](https://docs.microsoft.com/previous-versions/windows/xna/bb199616%28v%3dxnagamestudio.41%29) viene chiamato ripetutamente da XNA Framework durante l'esecuzione del gioco. Il metodo [Update](https://docs.microsoft.com/previous-versions/windows/xna/bb199616%28v%3dxnagamestudio.41%29) chiama i metodi **ProcessInertia** e **UpdateFromMouse** nella raccolta di parti del gioco. Questi metodi sono descritti in [Creazione della classe GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).  
  
 [!code-csharp[ManipulationXNA#_Game1_UpdateGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_updategame)]  
  
 Anche il metodo [Draw](https://docs.microsoft.com/previous-versions/windows/xna/bb196422%28v%3dxnagamestudio.41%29) viene chiamato ripetutamente da XNA Framework mentre il gioco è in esecuzione. Il metodo [Draw](https://docs.microsoft.com/previous-versions/windows/xna/bb196422%28v%3dxnagamestudio.41%29) esegue il rendering delle parti del gioco chiamando il metodo **Draw** dell'oggetto **GamePieceCollection**. Questo metodo viene descritto in [Creazione della classe GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).  
  
 [!code-csharp[ManipulationXNA#_Game1_DrawGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_drawgame)]  
  
## <a name="see-also"></a>Vedere anche  
 [Modifiche e inerzia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [Uso delle modifiche e dell'inerzia in un'applicazione XNA](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [Creazione della classe GamePiece](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [Creazione della classe GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
 [Listati di codice completi](../../../docs/framework/common-client-technologies/full-code-listings.md)
