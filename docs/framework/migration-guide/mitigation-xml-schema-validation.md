---
title: 'Attenuazione: Convalida di XML Schema'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
ms.openlocfilehash: 99cc1eae08697909d89e5c1e46cd604c7da543bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457746"
---
# <a name="mitigation-xml-schema-validation"></a>Attenuazione: Convalida di XML Schema
In .NET Framework 4.6 la convalida dello schema XSD rileva la violazione di vincoli univoci se viene usata una chiave composta e una chiave è vuota.  
  
## <a name="impact"></a>Impatto  
 L'impatto di questa modifica potrebbe essere minimo: basato sulla specifica dello schema, un errore di convalida dello schema è previsto se `xsd:unique` viene violato da una chiave composta con una chiave vuota.  
  
## <a name="mitigation"></a>Strategia di riduzione del rischio  
 La rilevazione di un errore di convalida dello schema se una chiave composta possiede una chiave vuota è una funzione configurabile:  
  
- A partire dalle app destinate a .NET Framework 4.6, la rilevazione dell'errore di convalida dello schema viene abilitata per impostazione predefinita; tuttavia, è possibile escluderla, in modo che l'errore di convalida dello schema non venga rilevato.  
  
- Nelle app eseguite in .NET Framework 4.6 ma destinate a .NET Framework 4.5.2 e versioni precedenti, la rilevazione di un errore di convalida dello schema non viene eseguita per impostazione predefinita; è possibile consentirla in modo che l'errore di convalida dello schema venga rilevato.  
  
 Questo comportamento può essere configurato usando la classe <xref:System.AppContext> per definire il valore dell'opzione `System.Xml.IgnoreEmptyKeySequences`. Dal momento che il valore predefinito dell'opzione è `false` (le sequenze di chiavi vuote non vengono ignorate), le app destinate a .NET Framework 4.6 possono escludere il comportamento usando il codice seguente per impostare il valore dell'opzione su `true`:  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 Per le app destinate a .NET Framework 4.5.2 e versioni precedenti, dal momento che il valore predefinito dell'opzione è `true` (le sequenze di chiavi vuote vengono ignorate), è possibile garantire che una chiave composta con una chiave vuota generi un errore di convalida dello schema usando il codice seguente per impostare il valore dell'opzione su `false`.  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Compatibilità tra le versioni](application-compatibility.md)
