---
title: "Procedura: Creare l'identità di un'entità personalizzata"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IPrincipal
- IAuthorizationPolicy
- PrincipalPermissionMode
- PrincipalPermissionAttribute
ms.assetid: c4845fca-0ed9-4adf-bbdc-10812be69b61
ms.openlocfilehash: 05a90c4020f225414b21e82684e46b3c2abda010
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797079"
---
# <a name="how-to-create-a-custom-principal-identity"></a>Procedura: Creare l'identità di un'entità personalizzata
<xref:System.Security.Permissions.PrincipalPermissionAttribute> è uno strumento dichiarativo per controllare l'accesso ai metodi del servizio. Quando si usa questo attributo, l'enumerazione <xref:System.ServiceModel.Description.PrincipalPermissionMode> specifica la modalità di esecuzione dei controlli dell'autorizzazione. Se questa modalità è impostata su <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>, consente all'utente di specificare che una classe <xref:System.Security.Principal.IPrincipal> personalizzata restituita dalla proprietà <xref:System.Threading.Thread.CurrentPrincipal%2A>. In questo argomento viene illustrato lo scenario in cui <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> viene usato in combinazione con un criterio di autorizzazione personalizzato e un'entità personalizzata.  
  
 Per ulteriori informazioni sull'utilizzo <xref:System.Security.Permissions.PrincipalPermissionAttribute>di, vedere [procedura: Limitare l'accesso con la classe](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)PrincipalPermissionAttribute.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[PrincipalPermissionMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/principalpermissionmode/cs/source.cs#8)]
 [!code-vb[PrincipalPermissionMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/principalpermissionmode/vb/source.vb#8)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare il codice sono necessari riferimenti agli spazi dei nomi seguenti:  
  
- <xref:System>  
  
- <xref:System.Collections.Generic>  
  
- <xref:System.Security.Permissions>  
  
- <xref:System.Security.Principal>  
  
- <xref:System.Threading>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.ServiceModel.Description>  
  
- <xref:System.IdentityModel.Claims>  
  
- <xref:System.IdentityModel.Policy>  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Description.PrincipalPermissionMode>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [Procedura: Usare il provider di ruoli ASP.NET con un servizio](../feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Procedura: Limitare l'accesso con la classe PrincipalPermissionAttribute](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)
