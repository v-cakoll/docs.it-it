---
title: Contratti di routing
ms.date: 03/30/2017
ms.assetid: 9ceea7ae-ea19-4cf9-ba4f-d071e236546d
ms.openlocfilehash: 73d303c95a636f5e90f256272726c08c581d6fdf
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43873416"
---
# <a name="routing-contracts"></a>Contratti di routing
I contratti routing definiscono i modelli di messaggio che possono essere elaborati dal servizio di routing.  Ogni contratto è sprovvisto di tipi e consente la ricezione di un messaggio da parte del servizio senza conoscere l'azione o lo schema del messaggio. In questo modo il servizio di routing può indirizzare in modo generico i messaggi senza ulteriore configurazione per le specifiche dei messaggi sottostanti indirizzati.  
  
## <a name="routing-contracts"></a>Contratti di routing  
 Poiché il servizio di routing accetta un oggetto WCF Message generico, la considerazione più importante in fase di scelta di un contratto ricade sulla forma del canale che verrà utilizzato per le comunicazioni con i client e i servizi. In caso di elaborazione di messaggi, il servizio di routing utilizza message pump simmetrici, quindi la forma del contratto in ingresso deve in genere corrispondere alla forma del contratto in uscita. Tuttavia, vi sono casi in cui il dispatcher del modello del servizio possa modificare le forme, ad esempio quando il dispatcher converte un canale duplex in un canale request / reply oppure rimuove il supporto della sessione da un canale quando non è obbligatorio e non è in uso (vale a dire Quando **SessionMode**, la conversione un' **IInputSessionChannel** in un **IInputChannel**).  
  
 Per supportare questi message pump, il servizio di routing fornisce contratti nello spazio dei nomi <xref:System.ServiceModel.Routing>, che deve essere utilizzato in caso di definizione degli endpoint servizio utilizzati dal servizio di routing. Questi contratti sono sprovvisti di tipi. In questo modo è possibile ricevere qualsiasi azione o tipo di messaggio e il servizio di routing può gestire i messaggi senza conoscere lo schema del messaggio specifico. Per altre informazioni sui contratti utilizzati dal servizio di Routing, vedere [contratti Routing](../../../../docs/framework/wcf/feature-details/routing-contracts.md).  
  
 I contratti forniti dal servizio di routing si trovano nello spazio dei nomi <xref:System.ServiceModel.Routing> e vengono descritti nella tabella seguente.  
  
|Contratto|Forma|Forma del canale|  
|--------------|-----------|-------------------|  
|<xref:System.ServiceModel.Routing.ISimplexDatagramRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputChannel -> IOutputChannel|  
|<xref:System.ServiceModel.Routing.ISimplexSessionRouter>|SessionMode = SessionMode.Required<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputSessionChannel -> IOutputSessionChannel|  
|<xref:System.ServiceModel.Routing.IRequestReplyRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true|IReplyChannel -> IRequestChannel|  
|<xref:System.ServiceModel.Routing.IDuplexSessionRouter>|SessionMode=SessionMode.Required<br /><br /> CallbackContract=typeof(ISimplexSession)<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true<br /><br /> TransactionFlow(TransactionFlowOption.Allowed)|IDuplexSessionChannel -> IDuplexSessionChannel|  
  
## <a name="see-also"></a>Vedere anche  
 [Servizio di routing](https://msdn.microsoft.com/library/5ac8718c-bcef-456f-bfd5-1e60a30d6eaa)  
 [Introduzione al routing](../../../../docs/framework/wcf/feature-details/routing-introduction.md)
