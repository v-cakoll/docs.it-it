---
ms.openlocfilehash: e7154919d6a09a04e650d5546feb2ae6c6cc912f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859073"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a>HttpRuntime.AppDomainAppPath genera un'eccezione NullReferenceException

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6.2, il runtime genera una <code>T:System.NullReferenceException</code> durante il recupero di un valore <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> che include caratteri Null. In .NET Framework 4.6.1 e versioni precedenti, il runtime genera una <code>T:System.ArgumentNullException</code>.|
|Suggerimento|È possibile eseguire una delle operazioni seguenti per rispondere a questa modifica:<ul><li>Se l'applicazione è in esecuzione in .NET Framework 4.6.2, gestire <code>T:System.NullReferenceException</code>.</li><li>Eseguire l'aggiornamento a .NET Framework 4.7, che consente di ripristinare il comportamento precedente e genera un'eccezione <code>T:System.ArgumentNullException</code>.</li></ul>|
|Scope|Microsoft Edge|
|Versione|4.6.2|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType></li></ul>|
