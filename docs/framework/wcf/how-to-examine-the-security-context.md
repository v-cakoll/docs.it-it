---
title: 'Procedura: esaminare il contesto di sicurezza'
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
- ServiceSecurityContext class
- WCF, security
- Claimset class
ms.assetid: 389b5a57-4175-4bc0-ada0-fc750d51149f
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 4d6852a3162b3a8666c711d455e72517a91c4477
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-examine-the-security-context"></a>Procedura: esaminare il contesto di sicurezza
Durante la programmazione di servizi [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], il contesto di sicurezza del servizio consente di determinare dettagli sulle credenziali client e sulle attestazioni utilizzate per l'autenticazione con il servizio. A tale fine, utilizzare le proprietà della classe <xref:System.ServiceModel.ServiceSecurityContext>.  
  
 È ad esempio possibile recuperare l'identità del client corrente utilizzando <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> o la proprietà <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>. Per determinare se il client è anonimo, utilizzare la proprietà <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A>.  
  
 È inoltre possibile determinare quali sono le attestazioni eseguite per conto del client eseguendo un'iterazione nella raccolta di attestazioni nella proprietà <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>.  
  
### <a name="to-get-the-current-security-context"></a>Per ottenere il contesto di sicurezza corrente  
  
-   Accedere alla proprietà <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> statica per ottenere il contesto di sicurezza corrente. Esaminare qualsiasi proprietà del contesto corrente dal riferimento.  
  
### <a name="to-determine-the-identity-of-the-caller"></a>Per determinare l'identità del chiamante  
  
1.  Stampare il valore delle proprietà <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> e <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>.  
  
### <a name="to-parse-the-claims-of-a-caller"></a>Per analizzare le attestazioni di un chiamante  
  
1.  Restituire la classe <xref:System.IdentityModel.Policy.AuthorizationContext> corrente. Utilizzare la proprietà <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> per restituire il contesto di sicurezza del servizio corrente, quindi restituire `AuthorizationContext` utilizzando la proprietà <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>.  
  
2.  Analizzare la raccolta di oggetti <xref:System.IdentityModel.Claims.ClaimSet> restituiti dalla proprietà <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> della classe <xref:System.IdentityModel.Policy.AuthorizationContext>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono stampati i valori delle proprietà <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> e <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> del contesto di sicurezza corrente e la proprietà <xref:System.IdentityModel.Claims.Claim.ClaimType%2A>, il valore della risorsa dell'attestazione e la proprietà <xref:System.IdentityModel.Claims.Claim.Right%2A> di ogni attestazione nel contesto di sicurezza corrente.  
  
 [!code-csharp[c_PrincipalPermissionAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#4)]
 [!code-vb[c_PrincipalPermissionAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#4)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Il codice utilizza gli spazi dei nomi seguenti:  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.IdentityModel.Policy>  
  
-   <xref:System.IdentityModel.Claims>  
  
## <a name="see-also"></a>Vedere anche  
 [Protezione dei servizi](../../../docs/framework/wcf/securing-services.md)  
 [Identità del servizio e autenticazione](../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
