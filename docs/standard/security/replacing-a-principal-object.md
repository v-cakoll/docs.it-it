---
title: Sostituzione di oggetti Principal
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET Framework], replacing principal objects
- security [.NET Framework], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 066176d39f04165d7882a3c295387847a46c8e6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="replacing-a-principal-object"></a><span data-ttu-id="e9557-102">Sostituzione di oggetti Principal</span><span class="sxs-lookup"><span data-stu-id="e9557-102">Replacing a Principal Object</span></span>
<span data-ttu-id="e9557-103">Le applicazioni che forniscono servizi di autenticazione devono poter sostituire l'oggetto **Principal** (<xref:System.Security.Principal.IPrincipal>) per un determinato thread.</span><span class="sxs-lookup"><span data-stu-id="e9557-103">Applications that provide authentication services must be able to replace the **Principal** object (<xref:System.Security.Principal.IPrincipal>) for a given thread.</span></span> <span data-ttu-id="e9557-104">Inoltre, il sistema di sicurezza deve garantire la possibilità di sostituire gli oggetti **Principal** perché un oggetto **Principal** non corretto collegato in modo intenzionalmente dannoso compromette la sicurezza dell'applicazione attestando un identità o un ruolo non true.</span><span class="sxs-lookup"><span data-stu-id="e9557-104">Furthermore, the security system must help protect the ability to replace **Principal** objects because a maliciously attached, incorrect **Principal** compromises the security of your application by claiming an untrue identity or role.</span></span> <span data-ttu-id="e9557-105">Pertanto, le applicazioni che richiedono la possibilità di sostituire **principale** oggetti devono essere concesse le <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> oggetto per il controllo dell'entità.</span><span class="sxs-lookup"><span data-stu-id="e9557-105">Therefore, applications that require the ability to replace **Principal** objects must be granted the <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> object for principal control.</span></span> <span data-ttu-id="e9557-106">Tenere presente che questa autorizzazione non è necessaria per eseguire controlli di sicurezza basata sui ruoli o per creare oggetti **Principal** .</span><span class="sxs-lookup"><span data-stu-id="e9557-106">(Note that this permission is not required for performing role-based security checks or for creating **Principal** objects.)</span></span>  
  
 <span data-ttu-id="e9557-107">L'oggetto **Principal** corrente può essere sostituito eseguendo le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9557-107">The current **Principal** object can be replaced by performing the following tasks:</span></span>  
  
1.  <span data-ttu-id="e9557-108">Creare l'oggetto **Principal** di sostituzione e l'oggetto **Identity** associato.</span><span class="sxs-lookup"><span data-stu-id="e9557-108">Create the replacement **Principal** object and associated **Identity** object.</span></span>  
  
2.  <span data-ttu-id="e9557-109">Associare il nuovo oggetto **Principal** al contesto chiamata.</span><span class="sxs-lookup"><span data-stu-id="e9557-109">Attach the new **Principal** object to the call context.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9557-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9557-110">Example</span></span>  
 <span data-ttu-id="e9557-111">L'esempio seguente illustra come creare un oggetto identità generico e usarlo per impostare l'identità di un thread.</span><span class="sxs-lookup"><span data-stu-id="e9557-111">The following example shows how to create a generic principal object and use it to set the principal of a thread.</span></span>  
  
 [!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
 [!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e9557-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9557-112">See Also</span></span>  
 <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>  
 [<span data-ttu-id="e9557-113">Oggetti Principal e Identity</span><span class="sxs-lookup"><span data-stu-id="e9557-113">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
