---
ms.openlocfilehash: 986b647047aaa4a185c1403e96e499ae587bea98
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617535"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a>HttpRuntime.AppDomainAppPath genera un'eccezione NullReferenceException

#### <a name="details"></a>Dettagli

In .NET Framework 4.6.2, il runtime genera una `T:System.NullReferenceException` durante il recupero di un valore `P:System.Web.HttpRuntime.AppDomainAppPath` che include caratteri Null. In .NET Framework 4.6.1 e versioni precedenti, il runtime genera una `T:System.ArgumentNullException`.

#### <a name="suggestion"></a>Suggerimento

È possibile eseguire una delle operazioni seguenti per rispondere a questa modifica:

- Se l'applicazione è in esecuzione in .NET Framework 4.6.2, gestire `T:System.NullReferenceException`.
- Eseguire l'aggiornamento a .NET Framework 4.7, che consente di ripristinare il comportamento precedente e genera un'eccezione `T:System.ArgumentNullException`.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.6.2       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType>
