---
ms.openlocfilehash: da79a19b3276f6fd2d679eb98406dd85e2a19948
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "70997643"
---
### <a name="apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>Possibili errori in Windows 2003 per le app pubblicate con ClickOnce che usano un certificato per la firma del codice SHA-256

|   |   |
|---|---|
|Dettagli|Il file eseguibile è firmato con SHA256. In precedenza, veniva firmato con SHA1 indipendentemente dal fatto che il certificato di firma del codice fosse SHA-1 o SHA-256. Si applica a:<ul><li>Tutte le applicazioni compilate con Visual Studio 2012 o versioni successive.</li><li>Applicazioni compilate con Visual Studio 2010 o versioni precedenti su sistemi in cui è presente .NET Framework 4.5.</li></ul>Se inoltre è presente .NET Framework 4.5 o versione successiva, il manifesto ClickOnce viene firmato anche con SHA-256 per i certificati SHA-256 indipendentemente dalla versione di .NET Framework per cui è stato compilato.|
|Suggerimento|La modifica della firma del file eseguibile di ClickOnce interessa solo i sistemi Windows Server 2003 in cui è richiesta l'installazione di quanto indicato nell'articolo 938397 della Knowledge Base. La modifica relativa alla firma del manifesto con SHA-256 anche quando un'app è destinata a .NET Framework 4.0 o a versioni precedenti introduce una dipendenza del runtime da .NET Framework 4.5 o da una versione successiva.|
|Scope|Microsoft Edge|
|Versione|4.5|
|Type|Ridestinazione|
