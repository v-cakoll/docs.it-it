---
ms.openlocfilehash: e7154919d6a09a04e650d5546feb2ae6c6cc912f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234935"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a>HttpRuntime.AppDomainAppPath genera un'eccezione NullReferenceException

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6.2, il runtime genera una <code>T:System.NullReferenceException</code> durante il recupero di un valore <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> che include caratteri Null. In .NET Framework 4.6.1 e versioni precedenti, il runtime genera una <code>T:System.ArgumentNullException</code>.|
|Suggerimento|È possibile eseguire una delle operazioni seguenti per rispondere a questa modifica:<ul><li>Se l'applicazione è in esecuzione in .NET Framework 4.6.2, gestire <code>T:System.NullReferenceException</code>.</li><li>Eseguire l'aggiornamento a .NET Framework 4.7, che consente di ripristinare il comportamento precedente e genera un'eccezione <code>T:System.ArgumentNullException</code>.</li></ul>|
|Ambito|Microsoft Edge|
|Versione|4.6.2|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType></li></ul>|
