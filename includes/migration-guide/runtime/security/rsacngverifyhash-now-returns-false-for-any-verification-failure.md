---
ms.openlocfilehash: fc315faef750d93d914104dd568078aa3fc430d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887786"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a>RSACng.VerifyHash ora restituisce False per qualsiasi errore di verifica

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.6.2, questo metodo restituisce **False** se la firma stessa non è formattata correttamente. Ora restituisce false per qualsiasi errore di verifica. In .NET Framework 4.6 e 4.6.1, il metodo genera <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> se non è formattata correttamente la firma stessa.|
|Suggerimento|Qualsiasi codice la cui esecuzione dipenda da <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> deve invece essere eseguito se la convalida non va a buon fine e il metodo restituisce **False**.|
|Scope|Minorenne|
|Versione|4.6.2|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
