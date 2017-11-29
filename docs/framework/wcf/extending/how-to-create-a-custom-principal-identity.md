---
title: "Procedura: creare l'identità di un'entità personalizzata"
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
- IPrincipal
- IAuthorizationPolicy
- PrincipalPermissionMode
- PrincipalPermissionAttribute
ms.assetid: c4845fca-0ed9-4adf-bbdc-10812be69b61
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 973b3ebbedf80a7c33047f74306232805989646c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-principal-identity"></a><span data-ttu-id="bed81-102">Procedura: creare l'identità di un'entità personalizzata</span><span class="sxs-lookup"><span data-stu-id="bed81-102">How to: Create a Custom Principal Identity</span></span>
<span data-ttu-id="bed81-103"><xref:System.Security.Permissions.PrincipalPermissionAttribute> è uno strumento dichiarativo per controllare l'accesso ai metodi del servizio.</span><span class="sxs-lookup"><span data-stu-id="bed81-103">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is a declarative means of controlling access to service methods.</span></span> <span data-ttu-id="bed81-104">Quando si usa questo attributo, l'enumerazione <xref:System.ServiceModel.Description.PrincipalPermissionMode> specifica la modalità di esecuzione dei controlli dell'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="bed81-104">When using this attribute, the <xref:System.ServiceModel.Description.PrincipalPermissionMode> enumeration specifies the mode for performing authorization checks.</span></span> <span data-ttu-id="bed81-105">Se questa modalità è impostata su <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>, consente all'utente di specificare che una classe <xref:System.Security.Principal.IPrincipal> personalizzata restituita dalla proprietà <xref:System.Threading.Thread.CurrentPrincipal%2A>.</span><span class="sxs-lookup"><span data-stu-id="bed81-105">When this mode is set to <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>, it enables the user to specify a custom <xref:System.Security.Principal.IPrincipal> class returned by the <xref:System.Threading.Thread.CurrentPrincipal%2A> property.</span></span> <span data-ttu-id="bed81-106">In questo argomento viene illustrato lo scenario in cui <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> viene usato in combinazione con un criterio di autorizzazione personalizzato e un'entità personalizzata.</span><span class="sxs-lookup"><span data-stu-id="bed81-106">This topic illustrates the scenario when <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> is used in combination with a custom authorization policy and a custom principal.</span></span>  
  
 <span data-ttu-id="bed81-107">Per ulteriori informazioni sull'utilizzo di <xref:System.Security.Permissions.PrincipalPermissionAttribute>, vedere [procedura: limitare l'accesso con la classe PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="bed81-107">For more information about using the <xref:System.Security.Permissions.PrincipalPermissionAttribute>, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bed81-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="bed81-108">Example</span></span>  
 [!code-csharp[PrincipalPermissionMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/principalpermissionmode/cs/source.cs#8)]
 [!code-vb[PrincipalPermissionMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/principalpermissionmode/vb/source.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bed81-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="bed81-109">Compiling the Code</span></span>  
 <span data-ttu-id="bed81-110">Per compilare il codice sono necessari riferimenti agli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bed81-110">References to the following namespaces are needed to compile the code:</span></span>  
  
-   <xref:System>  
  
-   <xref:System.Collections.Generic>  
  
-   <xref:System.Security.Permissions>  
  
-   <xref:System.Security.Principal>  
  
-   <xref:System.Threading>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Description>  
  
-   <xref:System.IdentityModel.Claims>  
  
-   <xref:System.IdentityModel.Policy>  
  
## <a name="see-also"></a><span data-ttu-id="bed81-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bed81-111">See Also</span></span>  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 [<span data-ttu-id="bed81-112">Procedura: utilizzare il Provider di ruoli ASP.NET con un servizio</span><span class="sxs-lookup"><span data-stu-id="bed81-112">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [<span data-ttu-id="bed81-113">Procedura: Limitare l'accesso con la classe PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="bed81-113">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
