---
title: 'Procedura: creare un endpoint del servizio nel codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3fbb22fa-2930-48b8-b437-def1de87c6a0
ms.openlocfilehash: 25ea843df7871d730926fe7b9aac9f21d58e263e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598931"
---
# <a name="how-to-create-a-service-endpoint-in-code"></a>Procedura: creare un endpoint del servizio nel codice
In questo esempio viene definito un contratto `ICalculator` per un servizio di calcolatrice. Il servizio viene implementato nella classe `CalculatorService` e il relativo endpoint viene quindi definito in codice, dove si specifica che il servizio deve utilizzare la classe <xref:System.ServiceModel.BasicHttpBinding>.  
  
 La procedura solitamente consigliata consiste nello specificare in modo dichiarativo l'associazione e le informazioni dell'indirizzo nella configurazione anziché in modo imperativo nel codice. In genere definire endpoint nel codice non è pratico in quanto le associazioni e gli indirizzi di un servizio distribuito sono solitamente diversi da quelli usati durante lo sviluppo del servizio. Più in generale, se le informazioni su associazione e indirizzo non vengono incluse nel codice, tali dati possono essere modificati senza dover compilare o distribuire nuovamente l'applicazione.  
  
#### <a name="to-create-a-service-endpoint-in-code"></a>Per creare un endpoint del servizio nel codice  
  
1. Creare l'interfaccia che definisce il contratto di servizio.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2. Implementare il contratto di servizio definito nel passaggio 1.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3. Nell'applicazione host, creare l'indirizzo di base del servizio e l'associazione da utilizzare con il servizio.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4. Creare l'host e chiamare <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=nameWithType> o uno degli altri overload per aggiungere l'endpoint del servizio per l'host.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#6)]
     [!code-vb[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#6)]  
  
     Per specificare l'associazione nel codice, ma per usare gli endpoint predefiniti forniti dal runtime, passare l'indirizzo di base al costruttore durante la creazione dell'oggetto <xref:System.ServiceModel.ServiceHost> e non chiamare <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A?displayProperty=nameWithType> .  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#7)]
     [!code-vb[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#7)]  
  
     Per ulteriori informazioni sugli endpoint predefiniti, vedere [Configurazione semplificata](../simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Specificare un'associazione al servizio nel codice](../how-to-specify-a-service-binding-in-code.md)
