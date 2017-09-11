---
title: 'Mitigazione: Costruttore ClaimsIdentity'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 946903f1-0fbf-4f67-805b-1eb48352024d
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a50cbd69aa1f2c72adc9fc4d10a070f5faa0cf54
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-claimsidentity-constructor"></a><span data-ttu-id="d81e3-102">Mitigazione: Costruttore ClaimsIdentity</span><span class="sxs-lookup"><span data-stu-id="d81e3-102">Mitigation: ClaimsIdentity Constructor</span></span>
<span data-ttu-id="d81e3-103">A partire da [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] è stato modificato il modo in cui il costruttore <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> imposta la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="d81e3-103">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], there is change in how the <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> constructor sets the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property.</span></span> <span data-ttu-id="d81e3-104">Se l'argomento <xref:System.Security.Principal.IIdentity> è un oggetto <xref:System.Security.Claims.ClaimsIdentity> e la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> di tale oggetto <xref:System.Security.Claims.ClaimsIdentity> non è `null`, la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> viene allegata usando il metodo <xref:System.Security.Claims.ClaimsIdentity.Clone%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="d81e3-104">If the <xref:System.Security.Principal.IIdentity> argument is a <xref:System.Security.Claims.ClaimsIdentity> object, and the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property of that <xref:System.Security.Claims.ClaimsIdentity> object is not `null`, the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property is attached by using the <xref:System.Security.Claims.ClaimsIdentity.Clone%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="d81e3-105">Nell'oggetto [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> è allegata come riferimento esistente.</span><span class="sxs-lookup"><span data-stu-id="d81e3-105">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property is attached as a  existing reference.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="d81e3-106">Impatto</span><span class="sxs-lookup"><span data-stu-id="d81e3-106">Impact</span></span>  
 <span data-ttu-id="d81e3-107">A partire da [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> del nuovo oggetto <xref:System.Security.Claims.ClaimsIdentity> non è uguale alla proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> dell'argomento <xref:System.Security.Principal.IIdentity> del costruttore.</span><span class="sxs-lookup"><span data-stu-id="d81e3-107">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property of the new <xref:System.Security.Claims.ClaimsIdentity> object is not equal to the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property of the constructor's <xref:System.Security.Principal.IIdentity> argument.</span></span> <span data-ttu-id="d81e3-108">In [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] e versioni precedenti, invece, è uguale.</span><span class="sxs-lookup"><span data-stu-id="d81e3-108">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, it is equal.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="d81e3-109">Attenuazione</span><span class="sxs-lookup"><span data-stu-id="d81e3-109">Mitigation</span></span>  
 <span data-ttu-id="d81e3-110">Se questo comportamento è inaccettabile, è possibile ripristinare il comportamento precedente impostando il commutatore `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` nel file di configurazione dell'applicazione su `true`.</span><span class="sxs-lookup"><span data-stu-id="d81e3-110">If this behavior is undesirable, you can restore the previous behavior by setting the `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` switch in your application configuration file to `true`.</span></span> <span data-ttu-id="d81e3-111">A questo scopo è necessario aggiungere il codice seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file web.config:</span><span class="sxs-lookup"><span data-stu-id="d81e3-111">This requires that you add the following to  the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your web.config file:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d81e3-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d81e3-112">See Also</span></span>  
 [<span data-ttu-id="d81e3-113">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="d81e3-113">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

