---
ms.openlocfilehash: fa5cf2280cdd9535962568a6272d047d261eeba5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621208"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a>RSACng.VerifyHash ora restituisce False per qualsiasi errore di verifica

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.6.2, questo metodo restituisce **False** se la firma stessa non è formattata correttamente. Ora restituisce false per qualsiasi errore di verifica. In .NET Framework 4.6 e 4.6.1, il metodo genera <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> se non è formattata correttamente la firma stessa.

#### <a name="suggestion"></a>Suggerimento

Qualsiasi codice la cui esecuzione dipenda da <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> deve invece essere eseguito se la convalida non va a buon fine e il metodo restituisce **False**.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.6.2|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
