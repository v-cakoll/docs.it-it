---
title: Autorizzazioni pericolose e amministrazione dei criteri
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ae24cdcb97e30da0bd4aec6569ef3dcda11488c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775765"
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="bbd9f-102">Autorizzazioni pericolose e amministrazione dei criteri</span><span class="sxs-lookup"><span data-stu-id="bbd9f-102">Dangerous Permissions and Policy Administration</span></span>
<span data-ttu-id="bbd9f-103">Diverse operazioni protette per le quali .NET Framework fornisce le autorizzazioni possono potenzialmente consentire l'elusione del sistema di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="bbd9f-103">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="bbd9f-104">Queste autorizzazioni pericolose devono essere fornite solo a codice attendibile e solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="bbd9f-104">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="bbd9f-105">Non esiste in genere alcuna difesa contro malware se viene concesso questo tipo di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="bbd9f-105">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbd9f-106">In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]sono state apportate importanti modifiche al modello di sicurezza e alla terminologia di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bbd9f-106">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="bbd9f-107">Per altre informazioni su queste modifiche, vedere [modifiche della sicurezza](../../../docs/framework/security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="bbd9f-107">For more information about these changes, see [Security Changes](../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="bbd9f-108">Le autorizzazioni pericolose sono illustrate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="bbd9f-108">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="bbd9f-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="bbd9f-109">Permission</span></span>|<span data-ttu-id="bbd9f-110">Potenziale rischio</span><span class="sxs-lookup"><span data-stu-id="bbd9f-110">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="bbd9f-111">Consente al codice gestito di chiamare codice non gestito, che molto spesso è pericoloso.</span><span class="sxs-lookup"><span data-stu-id="bbd9f-111">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="bbd9f-112">Senza verifica il codice può eseguire qualsiasi operazione.</span><span class="sxs-lookup"><span data-stu-id="bbd9f-112">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="bbd9f-113">Una prova non convalidata può eludere i criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="bbd9f-113">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="bbd9f-114">La capacità di modificare i criteri di sicurezza può disattivare la protezione.</span><span class="sxs-lookup"><span data-stu-id="bbd9f-114">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="bbd9f-115">L'uso della serializzazione può eludere i meccanismi di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="bbd9f-115">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="bbd9f-116">Per informazioni dettagliate, vedere [Sicurezza e serializzazione](../../../docs/framework/misc/security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="bbd9f-116">For details, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="bbd9f-117">La capacità di impostare l'entità corrente può eludere la sicurezza basata sui ruoli.</span><span class="sxs-lookup"><span data-stu-id="bbd9f-117">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="bbd9f-118">La modifica dei thread è pericolosa a causa dello stato di sicurezza associato ai thread.</span><span class="sxs-lookup"><span data-stu-id="bbd9f-118">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="bbd9f-119">Può usare i membri privati per aggirare i meccanismi di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="bbd9f-119">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bbd9f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbd9f-120">See also</span></span>

- [<span data-ttu-id="bbd9f-121">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="bbd9f-121">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
