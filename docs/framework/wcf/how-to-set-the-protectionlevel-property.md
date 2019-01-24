---
title: 'Procedura: Impostare la proprietà ProtectionLevel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
- ProtectionLevel property
ms.assetid: 3d4e8f80-0f9e-4a26-9899-beb6584e78df
ms.openlocfilehash: 13e07d06ed795bc50822d95cdd1ab44c6c336d2c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586856"
---
# <a name="how-to-set-the-protectionlevel-property"></a>Procedura: Impostare la proprietà ProtectionLevel
È possibile impostare il livello di protezione applicando un attributo appropriato e impostando la proprietà. È possibile impostare la protezione a livello di servizio su tutte le parti di ogni messaggio. In alternativa è possibile impostare la protezione a livelli granulari in modo crescente, dai metodi alle parti del messaggio. Per altre informazioni sul `ProtectionLevel` proprietà, vedere [livello di protezione delle informazioni sulle](../../../docs/framework/wcf/understanding-protection-level.md).  
  
> [!NOTE]
>  È possibile impostare i livelli di protezione solo nel codice, non nella configurazione.  
  
### <a name="to-sign-all-messages-for-a-service"></a>Per firmare tutti i messaggi per un servizio  
  
1.  Creare un'interfaccia per il servizio.  
  
2.  Applicare l'attributo <xref:System.ServiceModel.ServiceContractAttribute> al servizio e impostare la proprietà <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> su <xref:System.Net.Security.ProtectionLevel.Sign>, come illustrato nel codice seguente (il livello predefinito è <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>).  
  
     [!code-csharp[C_ProtectionLevel#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#1)]
     [!code-vb[C_ProtectionLevel#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#1)]  
  
### <a name="to-sign-all-message-parts-for-an-operation"></a>Per firmare tutte le parti del messaggio per un'operazione  
  
1.  Creare un'interfaccia per il servizio e applicarvi l'attributo <xref:System.ServiceModel.ServiceContractAttribute>.  
  
2.  Aggiungere una dichiarazione di metodo all'interfaccia.  
  
3.  Applicare l'attributo <xref:System.ServiceModel.OperationContractAttribute> al metodo e impostare la proprietà <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> su <xref:System.Net.Security.ProtectionLevel.Sign>, come illustrato nel codice seguente.  
  
     [!code-csharp[C_ProtectionLevel#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#2)]
     [!code-vb[C_ProtectionLevel#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#2)]  
  
## <a name="protecting-fault-messages"></a>Protezione dei messaggi di errore  
 È possibile inviare le eccezioni generate in un servizio a un client come errori SOAP. Per altre informazioni sulla creazione fortemente tipizzati errori, vedere [se si specifica e gestione degli errori in contratti e servizi](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md) e [come: Dichiarare errori nei contratti di servizio](../../../docs/framework/wcf/how-to-declare-faults-in-service-contracts.md).  
  
#### <a name="to-protect-a-fault-message"></a>Per proteggere i messaggi di errore  
  
1.  Creare un tipo che rappresenta il messaggio di errore. Nell'esempio seguente viene creata una classe denominata `MathFault` con due campi.  
  
2.  Applicare l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> al tipo e un attributo <xref:System.Runtime.Serialization.DataMemberAttribute> a ogni campo che deve essere serializzato, come illustrato nel codice seguente.  
  
     [!code-csharp[C_ProtectionLevel#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#3)]
     [!code-vb[C_ProtectionLevel#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#3)]  
  
3.  Nell'interfaccia che restituirà l'errore, applicare l'attributo <xref:System.ServiceModel.FaultContractAttribute> al metodo che restituirà l'errore e impostare il parametro `detailType` sul tipo della classe di errore.  
  
4.  Nel costruttore, inoltre, impostare la proprietà <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A> su <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, come illustrato nel codice seguente.  
  
     [!code-csharp[C_ProtectionLevel#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#4)]
     [!code-vb[C_ProtectionLevel#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#4)]  
  
## <a name="protecting-message-parts"></a>Protezione delle parti del messaggio  
 Utilizzare un contratto di messaggio per proteggere le parti di un messaggio. Per altre informazioni sui contratti di messaggio, vedere [Using Message Contracts](../../../docs/framework/wcf/feature-details/using-message-contracts.md).  
  
#### <a name="to-protect-a-message-body"></a>Per proteggere il corpo del messaggio  
  
1.  Creare un tipo che rappresenta il messaggio. Nell'esempio seguente viene creata una classe `Company` con due campi, `CompanyName` e `CompanyID`.  
  
2.  Applicare l'attributo <xref:System.ServiceModel.MessageContractAttribute> alla classe e impostare la proprietà <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A> su <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.  
  
3.  Applicare l'attributo <xref:System.ServiceModel.MessageHeaderAttribute> a un campo che verrà espresso come intestazione del messaggio e impostare la proprietà `ProtectionLevel` su <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.  
  
4.  Si applicano i <xref:System.ServiceModel.MessageBodyMemberAttribute> a qualsiasi campo che verrà espresso come parte del corpo del messaggio e impostare il `ProtectionLevel` proprietà <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, come illustrato nell'esempio seguente.  
  
     [!code-csharp[C_ProtectionLevel#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#5)]
     [!code-vb[C_ProtectionLevel#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#5)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene impostata la proprietà `ProtectionLevel` di diverse classi Attribute in varie posizioni di un servizio.  
  
 [!code-csharp[C_ProtectionLevel#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#6)]
 [!code-vb[C_ProtectionLevel#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#6)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Nel codice seguente vengono illustrati gli spazi dei nomi necessari per compilare il codice di esempio.  
  
 [!code-csharp[C_ProtectionLevel#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#0)]
 [!code-vb[C_ProtectionLevel#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#0)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.ServiceModel.MessageContractAttribute>
- <xref:System.ServiceModel.MessageBodyMemberAttribute>
- [Informazioni sul livello di protezione](../../../docs/framework/wcf/understanding-protection-level.md)
