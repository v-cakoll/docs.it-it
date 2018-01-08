---
title: 'Attenuazione: Convalida di XML Schema'
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
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9cd5e83da32e32b60f5d1584c7057e36a3851b8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-xml-schema-validation"></a><span data-ttu-id="15f95-102">Attenuazione: Convalida di XML Schema</span><span class="sxs-lookup"><span data-stu-id="15f95-102">Mitigation: XML Schema Validation</span></span>
<span data-ttu-id="15f95-103">In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] la convalida dello schema XSD rileva la violazione di vincoli univoci se viene usata una chiave composta e una chiave è vuota.</span><span class="sxs-lookup"><span data-stu-id="15f95-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], XSD schema validation detects a violation of the unique constraint if a compound key is used and one key is empty.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="15f95-104">Impatto</span><span class="sxs-lookup"><span data-stu-id="15f95-104">Impact</span></span>  
 <span data-ttu-id="15f95-105">L'impatto di questa modifica potrebbe essere minimo: basato sulla specifica dello schema, un errore di convalida dello schema è previsto se `xsd:unique` viene violato da una chiave composta con una chiave vuota.</span><span class="sxs-lookup"><span data-stu-id="15f95-105">The impact of this change should be minimal: based on the schema specification, a schema validation error is expected if `xsd:unique` is violated by using a compound key with an empty key.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="15f95-106">Mitigazione</span><span class="sxs-lookup"><span data-stu-id="15f95-106">Mitigation</span></span>  
 <span data-ttu-id="15f95-107">La rilevazione di un errore di convalida dello schema se una chiave composta possiede una chiave vuota è una funzione configurabile:</span><span class="sxs-lookup"><span data-stu-id="15f95-107">Whether a schema validation error is detected if a compound key has one empty key is a configurable feature:</span></span>  
  
-   <span data-ttu-id="15f95-108">A partire dalle app destinate a [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], la rilevazione dell'errore di convalida dello schema viene abilitata per impostazione predefinita; tuttavia, è possibile escluderla, in modo che l'errore di convalida dello schema non venga rilevato.</span><span class="sxs-lookup"><span data-stu-id="15f95-108">Starting with the apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], detection of the schema validation error is enabled by default; however, it is possible to opt out of it, so that the schema validation error will not be detected.</span></span>  
  
-   <span data-ttu-id="15f95-109">Nelle app eseguite in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ma destinate a [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] e versioni successive la rilevazione di un errore di convalida dello schema non viene eseguita per impostazione predefinita; è possibile consentirla in modo che l'errore di convalida dello schema venga rilevato.</span><span class="sxs-lookup"><span data-stu-id="15f95-109">In apps that run under the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] but target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, a schema validation error is not detected by default; however, it is possible to opt into it, so that the schema validation error will be detected.</span></span>  
  
 <span data-ttu-id="15f95-110">Questo comportamento può essere configurato usando la classe <xref:System.AppContext> per definire il valore dell'opzione `System.Xml.IgnoreEmptyKeySequences`.</span><span class="sxs-lookup"><span data-stu-id="15f95-110">This behavior can be configured by using the <xref:System.AppContext> class to define the value of the `System.Xml.IgnoreEmptyKeySequences` switch.</span></span> <span data-ttu-id="15f95-111">Dal momento che il valore predefinito dell'opzione è `false` (le sequenze di tasti vuote non vengono ignorate), le app destinate a [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] possono escludere il comportamento usando il codice seguente per impostare il valore dell'opzione su `true`:</span><span class="sxs-lookup"><span data-stu-id="15f95-111">Because the switch's default value is `false` (empty key sequences are not ignored), apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] can opt out of the behavior by using the following code to set the switch's value to `true`:</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 <span data-ttu-id="15f95-112">Per le app destinate a [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] e versioni precedenti, dal momento che il valore predefinito dell'opzione è `true` (le sequenze vuote di chiavi vengono ignorate), è possibile garantire che una chiave composta con una chiave vuota generi un errore di convalida dello schema usando il codice seguente per impostare il valore dell'opzione su `false`.</span><span class="sxs-lookup"><span data-stu-id="15f95-112">For apps that target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, because the switch's default value is `true` (empty key sequences are ignored), it is possible to ensure that a compound key with an empty key does generate a schema validation error by using the following code to set the switch's value to `false`.</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="15f95-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15f95-113">See Also</span></span>  
 [<span data-ttu-id="15f95-114">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="15f95-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
