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
ms.openlocfilehash: 324537ac018086669abccc21235f9a9359b413cb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662838"
---
# <a name="how-to-create-a-custom-principal-identity"></a><span data-ttu-id="40cd3-102">Procedura: Creare l'identità di un'entità personalizzata</span><span class="sxs-lookup"><span data-stu-id="40cd3-102">How to: Create a Custom Principal Identity</span></span>
<span data-ttu-id="40cd3-103"><xref:System.Security.Permissions.PrincipalPermissionAttribute> è uno strumento dichiarativo per controllare l'accesso ai metodi del servizio.</span><span class="sxs-lookup"><span data-stu-id="40cd3-103">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is a declarative means of controlling access to service methods.</span></span> <span data-ttu-id="40cd3-104">Quando si usa questo attributo, l'enumerazione <xref:System.ServiceModel.Description.PrincipalPermissionMode> specifica la modalità di esecuzione dei controlli dell'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="40cd3-104">When using this attribute, the <xref:System.ServiceModel.Description.PrincipalPermissionMode> enumeration specifies the mode for performing authorization checks.</span></span> <span data-ttu-id="40cd3-105">Se questa modalità è impostata su <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>, consente all'utente di specificare che una classe <xref:System.Security.Principal.IPrincipal> personalizzata restituita dalla proprietà <xref:System.Threading.Thread.CurrentPrincipal%2A>.</span><span class="sxs-lookup"><span data-stu-id="40cd3-105">When this mode is set to <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>, it enables the user to specify a custom <xref:System.Security.Principal.IPrincipal> class returned by the <xref:System.Threading.Thread.CurrentPrincipal%2A> property.</span></span> <span data-ttu-id="40cd3-106">In questo argomento viene illustrato lo scenario in cui <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> viene usato in combinazione con un criterio di autorizzazione personalizzato e un'entità personalizzata.</span><span class="sxs-lookup"><span data-stu-id="40cd3-106">This topic illustrates the scenario when <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> is used in combination with a custom authorization policy and a custom principal.</span></span>  
  
 <span data-ttu-id="40cd3-107">Per altre informazioni sull'uso di <xref:System.Security.Permissions.PrincipalPermissionAttribute>, vedere [come: Limitare l'accesso con la classe PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="40cd3-107">For more information about using the <xref:System.Security.Permissions.PrincipalPermissionAttribute>, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="40cd3-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="40cd3-108">Example</span></span>  
 [!code-csharp[PrincipalPermissionMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/principalpermissionmode/cs/source.cs#8)]
 [!code-vb[PrincipalPermissionMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/principalpermissionmode/vb/source.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="40cd3-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="40cd3-109">Compiling the Code</span></span>  
 <span data-ttu-id="40cd3-110">Per compilare il codice sono necessari riferimenti agli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="40cd3-110">References to the following namespaces are needed to compile the code:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="40cd3-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40cd3-111">See also</span></span>

- <xref:System.ServiceModel.Description.PrincipalPermissionMode>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [<span data-ttu-id="40cd3-112">Procedura: Usare il Provider di ruoli ASP.NET con un servizio</span><span class="sxs-lookup"><span data-stu-id="40cd3-112">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="40cd3-113">Procedura: Limitare l'accesso con la classe PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="40cd3-113">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
