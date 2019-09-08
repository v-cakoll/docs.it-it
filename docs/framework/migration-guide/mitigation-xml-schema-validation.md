---
title: 'Mitigazione: Convalida di XML Schema'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7f53a2e8684029c0d1329d29a88bd1788e62d43
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70789672"
---
# <a name="mitigation-xml-schema-validation"></a><span data-ttu-id="19ac6-102">Mitigazione: Convalida di XML Schema</span><span class="sxs-lookup"><span data-stu-id="19ac6-102">Mitigation: XML Schema Validation</span></span>
<span data-ttu-id="19ac6-103">In .NET Framework 4.6 la convalida dello schema XSD rileva la violazione di vincoli univoci se viene usata una chiave composta e una chiave è vuota.</span><span class="sxs-lookup"><span data-stu-id="19ac6-103">In the .NET Framework 4.6, XSD schema validation detects a violation of the unique constraint if a compound key is used and one key is empty.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="19ac6-104">Impatto</span><span class="sxs-lookup"><span data-stu-id="19ac6-104">Impact</span></span>  
 <span data-ttu-id="19ac6-105">L'impatto di questa modifica potrebbe essere minimo: basato sulla specifica dello schema, un errore di convalida dello schema è previsto se `xsd:unique` viene violato da una chiave composta con una chiave vuota.</span><span class="sxs-lookup"><span data-stu-id="19ac6-105">The impact of this change should be minimal: based on the schema specification, a schema validation error is expected if `xsd:unique` is violated by using a compound key with an empty key.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="19ac6-106">Mitigazione</span><span class="sxs-lookup"><span data-stu-id="19ac6-106">Mitigation</span></span>  
 <span data-ttu-id="19ac6-107">La rilevazione di un errore di convalida dello schema se una chiave composta possiede una chiave vuota è una funzione configurabile:</span><span class="sxs-lookup"><span data-stu-id="19ac6-107">Whether a schema validation error is detected if a compound key has one empty key is a configurable feature:</span></span>  
  
- <span data-ttu-id="19ac6-108">A partire dalle app destinate a .NET Framework 4.6, la rilevazione dell'errore di convalida dello schema viene abilitata per impostazione predefinita; tuttavia, è possibile escluderla, in modo che l'errore di convalida dello schema non venga rilevato.</span><span class="sxs-lookup"><span data-stu-id="19ac6-108">Starting with the apps that target the .NET Framework 4.6, detection of the schema validation error is enabled by default; however, it is possible to opt out of it, so that the schema validation error will not be detected.</span></span>  
  
- <span data-ttu-id="19ac6-109">Nelle app eseguite in .NET Framework 4.6 ma destinate a .NET Framework 4.5.2 e versioni precedenti, la rilevazione di un errore di convalida dello schema non viene eseguita per impostazione predefinita; è possibile consentirla in modo che l'errore di convalida dello schema venga rilevato.</span><span class="sxs-lookup"><span data-stu-id="19ac6-109">In apps that run under the .NET Framework 4.6 but target the .NET Framework 4.5.2 and earlier versions, a schema validation error is not detected by default; however, it is possible to opt into it, so that the schema validation error will be detected.</span></span>  
  
 <span data-ttu-id="19ac6-110">Questo comportamento può essere configurato usando la classe <xref:System.AppContext> per definire il valore dell'opzione `System.Xml.IgnoreEmptyKeySequences`.</span><span class="sxs-lookup"><span data-stu-id="19ac6-110">This behavior can be configured by using the <xref:System.AppContext> class to define the value of the `System.Xml.IgnoreEmptyKeySequences` switch.</span></span> <span data-ttu-id="19ac6-111">Dal momento che il valore predefinito dell'opzione è `false` (le sequenze di chiavi vuote non vengono ignorate), le app destinate a .NET Framework 4.6 possono escludere il comportamento usando il codice seguente per impostare il valore dell'opzione su `true`:</span><span class="sxs-lookup"><span data-stu-id="19ac6-111">Because the switch's default value is `false` (empty key sequences are not ignored), apps that target the .NET Framework 4.6 can opt out of the behavior by using the following code to set the switch's value to `true`:</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 <span data-ttu-id="19ac6-112">Per le app destinate a .NET Framework 4.5.2 e versioni precedenti, dal momento che il valore predefinito dell'opzione è `true` (le sequenze di chiavi vuote vengono ignorate), è possibile garantire che una chiave composta con una chiave vuota generi un errore di convalida dello schema usando il codice seguente per impostare il valore dell'opzione su `false`.</span><span class="sxs-lookup"><span data-stu-id="19ac6-112">For apps that target the .NET Framework 4.5.2 and earlier versions, because the switch's default value is `true` (empty key sequences are ignored), it is possible to ensure that a compound key with an empty key does generate a schema validation error by using the following code to set the switch's value to `false`.</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="19ac6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19ac6-113">See also</span></span>

- [<span data-ttu-id="19ac6-114">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="19ac6-114">Retargeting Changes</span></span>](retargeting-changes-in-the-net-framework-4-6.md)
