---
title: "Procedura: usare più token di sicurezza dello stesso tipo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9827d43ba4b0693d16380d93b066948d464bb978
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a>Procedura: usare più token di sicurezza dello stesso tipo
-   In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0 un messaggio del client contiene solo un token di un determinato tipo. Nella nuova versione, i messaggi del client possono contenere più token di uno stesso tipo. In questo argomento viene illustrato come includere più token dello stesso tipo in un messaggio del client.  
  
-   Si noti che non è possibile configurare un servizio in questo modo, in quanto un servizio può contenere un solo token di supporto.  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a>Per usare più token di sicurezza dello stesso tipo  
  
1.  Creare una raccolta di elementi di associazione vuota in cui inserire i dati.  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2.  Creare una classe <xref:System.ServiceModel.Channels.SecurityBindingElement> chiamando <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3.  Creare una raccolta <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters>.  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4.  Aggiungere i token SAML alla raccolta.  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5.  Aggiungere la raccolta alla classe <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6.  Aggiungere gli elementi di associazione alla relativa raccolta.  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7.  Restituire una nuova associazione personalizzata creata a partire dalla raccolta di elementi di associazione.  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato l'intero metodo descritto nella procedura precedente.  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
  
## <a name="see-also"></a>Vedere anche  
 [Architettura di sicurezza](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)
