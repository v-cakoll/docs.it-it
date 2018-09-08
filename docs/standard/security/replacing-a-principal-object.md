---
title: Sostituzione di oggetti Principal
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET Framework], replacing principal objects
- security [.NET Framework], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bfcd912fc16aa8d4b89a4f455d65b0294593cead
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44205854"
---
# <a name="replacing-a-principal-object"></a><span data-ttu-id="b40fe-102">Sostituzione di oggetti Principal</span><span class="sxs-lookup"><span data-stu-id="b40fe-102">Replacing a Principal Object</span></span>
<span data-ttu-id="b40fe-103">Le applicazioni che forniscono servizi di autenticazione devono poter sostituire l'oggetto **Principal** (<xref:System.Security.Principal.IPrincipal>) per un determinato thread.</span><span class="sxs-lookup"><span data-stu-id="b40fe-103">Applications that provide authentication services must be able to replace the **Principal** object (<xref:System.Security.Principal.IPrincipal>) for a given thread.</span></span> <span data-ttu-id="b40fe-104">Inoltre, il sistema di sicurezza deve garantire la possibilità di sostituire gli oggetti **Principal** perché un oggetto **Principal** non corretto collegato in modo intenzionalmente dannoso compromette la sicurezza dell'applicazione attestando un identità o un ruolo non true.</span><span class="sxs-lookup"><span data-stu-id="b40fe-104">Furthermore, the security system must help protect the ability to replace **Principal** objects because a maliciously attached, incorrect **Principal** compromises the security of your application by claiming an untrue identity or role.</span></span> <span data-ttu-id="b40fe-105">Di conseguenza, le applicazioni che richiedono la possibilità di sostituire **Principal** gli oggetti devono essere concesse le <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> oggetto per il controllo dell'entità.</span><span class="sxs-lookup"><span data-stu-id="b40fe-105">Therefore, applications that require the ability to replace **Principal** objects must be granted the <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> object for principal control.</span></span> <span data-ttu-id="b40fe-106">Tenere presente che questa autorizzazione non è necessaria per eseguire controlli di sicurezza basata sui ruoli o per creare oggetti **Principal** .</span><span class="sxs-lookup"><span data-stu-id="b40fe-106">(Note that this permission is not required for performing role-based security checks or for creating **Principal** objects.)</span></span>  
  
 <span data-ttu-id="b40fe-107">L'oggetto **Principal** corrente può essere sostituito eseguendo le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="b40fe-107">The current **Principal** object can be replaced by performing the following tasks:</span></span>  
  
1.  <span data-ttu-id="b40fe-108">Creare l'oggetto **Principal** di sostituzione e l'oggetto **Identity** associato.</span><span class="sxs-lookup"><span data-stu-id="b40fe-108">Create the replacement **Principal** object and associated **Identity** object.</span></span>  
  
2.  <span data-ttu-id="b40fe-109">Associare il nuovo oggetto **Principal** al contesto chiamata.</span><span class="sxs-lookup"><span data-stu-id="b40fe-109">Attach the new **Principal** object to the call context.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b40fe-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="b40fe-110">Example</span></span>  
 <span data-ttu-id="b40fe-111">L'esempio seguente illustra come creare un oggetto identità generico e usarlo per impostare l'identità di un thread.</span><span class="sxs-lookup"><span data-stu-id="b40fe-111">The following example shows how to create a generic principal object and use it to set the principal of a thread.</span></span>  
  
 [!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
 [!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b40fe-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b40fe-112">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>  
- [<span data-ttu-id="b40fe-113">Oggetti Principal e Identity</span><span class="sxs-lookup"><span data-stu-id="b40fe-113">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
