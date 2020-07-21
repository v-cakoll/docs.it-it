---
title: 'Attenuazione: Convalida di XML Schema'
description: La convalida dello schema XSD rileva una violazione del vincolo UNIQUE se viene utilizzata una chiave composta e una chiave è vuota nel .NET Framework 4,6.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
ms.openlocfilehash: 0672361ca5c0bc7cb6ec166f59278b93555e0947
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475307"
---
# <a name="mitigation-xml-schema-validation"></a><span data-ttu-id="0c7a1-103">Attenuazione: Convalida di XML Schema</span><span class="sxs-lookup"><span data-stu-id="0c7a1-103">Mitigation: XML Schema Validation</span></span>
<span data-ttu-id="0c7a1-104">In .NET Framework 4.6 la convalida dello schema XSD rileva la violazione di vincoli univoci se viene usata una chiave composta e una chiave è vuota.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-104">In the .NET Framework 4.6, XSD schema validation detects a violation of the unique constraint if a compound key is used and one key is empty.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="0c7a1-105">Impatto</span><span class="sxs-lookup"><span data-stu-id="0c7a1-105">Impact</span></span>  
 <span data-ttu-id="0c7a1-106">L'impatto di questa modifica potrebbe essere minimo: basato sulla specifica dello schema, un errore di convalida dello schema è previsto se `xsd:unique` viene violato da una chiave composta con una chiave vuota.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-106">The impact of this change should be minimal: based on the schema specification, a schema validation error is expected if `xsd:unique` is violated by using a compound key with an empty key.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="0c7a1-107">Strategia di riduzione del rischio</span><span class="sxs-lookup"><span data-stu-id="0c7a1-107">Mitigation</span></span>  
 <span data-ttu-id="0c7a1-108">La rilevazione di un errore di convalida dello schema se una chiave composta possiede una chiave vuota è una funzione configurabile:</span><span class="sxs-lookup"><span data-stu-id="0c7a1-108">Whether a schema validation error is detected if a compound key has one empty key is a configurable feature:</span></span>  
  
- <span data-ttu-id="0c7a1-109">A partire dalle app destinate a .NET Framework 4.6, la rilevazione dell'errore di convalida dello schema viene abilitata per impostazione predefinita; tuttavia, è possibile escluderla, in modo che l'errore di convalida dello schema non venga rilevato.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-109">Starting with the apps that target the .NET Framework 4.6, detection of the schema validation error is enabled by default; however, it is possible to opt out of it, so that the schema validation error will not be detected.</span></span>  
  
- <span data-ttu-id="0c7a1-110">Nelle app eseguite in .NET Framework 4.6 ma destinate a .NET Framework 4.5.2 e versioni precedenti, la rilevazione di un errore di convalida dello schema non viene eseguita per impostazione predefinita; è possibile consentirla in modo che l'errore di convalida dello schema venga rilevato.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-110">In apps that run under the .NET Framework 4.6 but target the .NET Framework 4.5.2 and earlier versions, a schema validation error is not detected by default; however, it is possible to opt into it, so that the schema validation error will be detected.</span></span>  
  
 <span data-ttu-id="0c7a1-111">Questo comportamento può essere configurato usando la classe <xref:System.AppContext> per definire il valore dell'opzione `System.Xml.IgnoreEmptyKeySequences`.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-111">This behavior can be configured by using the <xref:System.AppContext> class to define the value of the `System.Xml.IgnoreEmptyKeySequences` switch.</span></span> <span data-ttu-id="0c7a1-112">Dal momento che il valore predefinito dell'opzione è `false` (le sequenze di chiavi vuote non vengono ignorate), le app destinate a .NET Framework 4.6 possono escludere il comportamento usando il codice seguente per impostare il valore dell'opzione su `true`:</span><span class="sxs-lookup"><span data-stu-id="0c7a1-112">Because the switch's default value is `false` (empty key sequences are not ignored), apps that target the .NET Framework 4.6 can opt out of the behavior by using the following code to set the switch's value to `true`:</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 <span data-ttu-id="0c7a1-113">Per le app destinate a .NET Framework 4.5.2 e versioni precedenti, dal momento che il valore predefinito dell'opzione è `true` (le sequenze di chiavi vuote vengono ignorate), è possibile garantire che una chiave composta con una chiave vuota generi un errore di convalida dello schema usando il codice seguente per impostare il valore dell'opzione su `false`.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-113">For apps that target the .NET Framework 4.5.2 and earlier versions, because the switch's default value is `true` (empty key sequences are ignored), it is possible to ensure that a compound key with an empty key does generate a schema validation error by using the following code to set the switch's value to `false`.</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0c7a1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c7a1-114">See also</span></span>

- [<span data-ttu-id="0c7a1-115">Compatibilità tra le versioni</span><span class="sxs-lookup"><span data-stu-id="0c7a1-115">Application compatibility</span></span>](application-compatibility.md)
