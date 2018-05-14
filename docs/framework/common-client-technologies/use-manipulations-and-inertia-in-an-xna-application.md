---
title: Utilizzo delle modifiche e dell'inerzia in un'applicazione XNA
ms.date: 03/30/2017
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
ms.openlocfilehash: 78deee127f43aac71a1a4daaab808598065c2fe5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="using-manipulations-and-inertia-in-an-xna-application"></a>Utilizzo delle modifiche e dell'inerzia in un'applicazione XNA
Questo articolo descrive come è possibile usare l'elaborazione basata sulle modifiche e sull'inerzia in un'applicazione Microsoft XNA per controllare il movimento delle parti del gioco. Prima di leggere questo articolo, è necessario conoscere l'argomento [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) (Panoramica delle modifiche e dell'inerzia) e i concetti di programmazione XNA di base.  
  
 Per eseguire le attività descritte in questo articolo, il progetto XNA deve fare riferimento all'assembly <xref:System.Windows.Input.Manipulations> e [XNA Game Studio](http://msdn.microsoft.com/library/bb200104.aspx) ([download](http://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)) deve essere installato nel computer per consentire al progetto di fare riferimento agli assembly XNA.  
  
## <a name="overview-of-functionality"></a>Panoramica delle funzionalità  
 Questo articolo mostra come creare una classe personalizzata che rappresenta una parte del gioco che usa l'elaborazione basata sull'inerzia e sulle modifiche. Questa classe consente di modificare una parte del gioco sullo schermo trascinandola con il mouse e quindi rilasciandola. Una volta rilasciata, l'elaborazione basata sull'inerzia fa muovere la parte del gioco come se stesse rallentando gradualmente. Il movimento è sia lineare che angolare.  
  
 ![Semplice applicazione di modifiche e inerzia.](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")  
  
 Inoltre, viene creata una raccolta personalizzata che gestisce più parti del gioco. Ciò semplifica la gestione richiesta dalla classe XNA Game.  
  
 [Creazione della classe GamePiece](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [Creazione della classe GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [Creazione della classe Game1](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [Listati di codice completi](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Input.Manipulations>  
 [Informazioni generali sulle modifiche e sull'inerzia](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)
