---
title: 'Procedura: modificare il Provider di crittografia per un certificato x. 509 &#39; s la chiave privata'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptographic provider [WCF], changing
- cryptographic provider [WCF]
ms.assetid: b4254406-272e-4774-bd61-27e39bbb6c12
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e7dea9834b654be0b86155e18524053efa4b778b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-change-the-cryptographic-provider-for-an-x509-certificate39s-private-key"></a>Procedura: modificare il Provider di crittografia per un certificato x. 509 &#39; s la chiave privata
In questo argomento viene illustrato come modificare il provider di crittografia usato per fornire la chiave privata di un certificato X.509 e come integrare il provider nel framework di sicurezza di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Per ulteriori informazioni sull'utilizzo dei certificati, vedere [utilizzo dei certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
 Il [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] framework di sicurezza consente di introdurre nuovi tipi di token di sicurezza, come descritto in modo [procedura: creare un Token personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md). È anche possibile usare un token personalizzato per sostituire tipi di token esistenti forniti dal sistema.  
  
 In questo argomento, il token di sicurezza X.509 fornito dal sistema viene sostituito da un token X.509 personalizzato che prevede un'implementazione diversa per la chiave privata del certificato. Ciò è utile negli scenari in cui l'effettiva chiave privata viene fornita da un provider di crittografia diverso rispetto a quello predefinito di Windows. Un esempio di provider di crittografia alternativo è un modulo di sicurezza hardware che esegue tutte le operazioni di crittografia relative alla chiave privata e non archivia le chiavi private in memoria, migliorando così la protezione del sistema.  
  
 L'esempio seguente è solo per scopi dimostrativi. Il provider di crittografia di Windows predefinito non viene sostituito, bensì indica dove è possibile integrare tale provider.  
  
## <a name="procedures"></a>Procedure  
 Ogni token di sicurezza a cui sono associate una o più chiavi di sicurezza deve implementare la proprietà <xref:System.IdentityModel.Tokens.SecurityToken.SecurityKeys%2A> che restituisce una raccolta di chiavi dall'istanza del token di sicurezza. Se il token è un token di sicurezza X.509, la raccolta contiene una sola istanza della classe <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey> che rappresenta sia la chiave pubblica che la chiave privata associata al certificato. Per sostituire il provider di crittografia predefinito usato per fornire le chiavi del certificato, creare una nuova implementazione di questa classe.  
  
#### <a name="to-create-a-custom-x509-asymmetric-key"></a>Per creare una chiave asimmetrica X.509 personalizzata  
  
1.  Definire una nuova classe derivata dalla classe <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>.  
  
2.  Eseguire l'override della proprietà di sola lettura <xref:System.IdentityModel.Tokens.SecurityKey.KeySize%2A>. Questa proprietà restituisce le dimensioni effettive della chiave nella coppia di chiavi pubblica/privata del certificato.  
  
3.  Eseguire l'override del metodo <xref:System.IdentityModel.Tokens.SecurityKey.DecryptKey%2A>. Questo metodo viene chiamato dal framework di sicurezza di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per decifrare una chiave simmetrica con la chiave privata del certificato (la chiave precedentemente crittografata con la chiave pubblica del certificato).  
  
4.  Eseguire l'override del metodo <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetAsymmetricAlgorithm%2A>. Questo metodo viene chiamato dal framework della protezione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per ottenere un'istanza della classe <xref:System.Security.Cryptography.AsymmetricAlgorithm> che rappresenta il provider di crittografia per la chiave pubblica o privata del certificato, a seconda dei parametri passati al metodo.  
  
5.  Parametro facoltativo. Eseguire l'override del metodo <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetHashAlgorithmForSignature%2A>. Eseguire l'override di questo metodo se è richiesta un'implementazione diversa della classe <xref:System.Security.Cryptography.HashAlgorithm>.  
  
6.  Eseguire l'override del metodo <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetSignatureFormatter%2A>. Questo metodo restituisce un'istanza della classe <xref:System.Security.Cryptography.AsymmetricSignatureFormatter> associata alla chiave privata del certificato.  
  
7.  Eseguire l'override del metodo <xref:System.IdentityModel.Tokens.SecurityKey.IsSupportedAlgorithm%2A>. Questo metodo viene usato per indicare se un particolare algoritmo di crittografia è supportato dall'implementazione della chiave di sicurezza.  
  
     [!code-csharp[c_CustomX509Token#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#1)]
     [!code-vb[c_CustomX509Token#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#1)]  
  
 Nella procedura seguente viene illustrato come integrare l'implementazione della chiave di sicurezza asimmetrica X.509 personalizzata creata nella procedura precedente con il framework di sicurezza di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per sostituire il token di sicurezza X.509 fornito dal sistema.  
  
#### <a name="to-replace-the-system-provided-x509-security-token-with-a-custom-x509-asymmetric-security-key-token"></a>Per sostituire il token di sicurezza X.509 fornito dal sistema con una chiave di sicurezza asimmetrica X.509 personalizzata  
  
1.  Creare un token di sicurezza X.509 personalizzato che restituisce la chiave di sicurezza asimmetrica X.509 personalizzata anziché la chiave di sicurezza fornita dal sistema, come illustrato nell'esempio seguente. Per ulteriori informazioni sui token di sicurezza personalizzato, vedere [procedura: creare un Token personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
     [!code-csharp[c_CustomX509Token#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#2)]
     [!code-vb[c_CustomX509Token#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#2)]  
  
2.  Creare un provider del token di sicurezza personalizzato che restituisca un token di sicurezza X.509 personalizzato, come illustrato nell'esempio. Per ulteriori informazioni sui provider di token di sicurezza personalizzato, vedere [procedura: creare un Provider di Token di sicurezza personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md).  
  
     [!code-csharp[c_CustomX509Token#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#3)]
     [!code-vb[c_CustomX509Token#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#3)]  
  
3.  Se è necessario usare la chiave di sicurezza personalizzata sul lato dell'iniziatore, creare un gestore del token di sicurezza client personalizzato e classi delle credenziali client personalizzate, come illustrato nell'esempio seguente. Per ulteriori informazioni sulle credenziali client personalizzate e responsabili dei token di protezione di client, vedere [procedura dettagliata: creazione di Client personalizzato e credenziali del servizio](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
     [!code-csharp[c_CustomX509Token#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#4)]
     [!code-vb[c_CustomX509Token#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#4)]  
  
     [!code-csharp[c_CustomX509Token#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#6)]
     [!code-vb[c_CustomX509Token#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#6)]  
  
4.  Se è necessario usare la chiave di sicurezza personalizzata sul lato del destinatario, creare un gestore del token di sicurezza del servizio personalizzato e credenziali del servizio personalizzate, come illustrato nell'esempio seguente. Per ulteriori informazioni sulle credenziali del servizio personalizzate e di service Manager token di sicurezza, vedere [procedura dettagliata: creazione di Client personalizzato e credenziali del servizio](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
     [!code-csharp[c_CustomX509Token#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#5)]
     [!code-vb[c_CustomX509Token#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#5)]  
  
     [!code-csharp[c_CustomX509Token#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#7)]
     [!code-vb[c_CustomX509Token#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#7)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>  
 <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey>  
 <xref:System.IdentityModel.Tokens.SecurityKey>  
 <xref:System.Security.Cryptography.AsymmetricAlgorithm>  
 <xref:System.Security.Cryptography.HashAlgorithm>  
 <xref:System.Security.Cryptography.AsymmetricSignatureFormatter>  
 [Procedura dettagliata: creazione di credenziali client e del servizio personalizzate](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [Procedura: Creare un autenticatore del token di sicurezza personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 [Procedura: Creare un provider di token di sicurezza personalizzati](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 [Procedura: Creare un token personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)  
 [Architettura di sicurezza](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
