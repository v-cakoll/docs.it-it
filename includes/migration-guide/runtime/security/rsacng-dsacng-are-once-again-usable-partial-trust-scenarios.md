---
ms.openlocfilehash: e92cbb7decb5e530bbf611cec26ce03a05e06eb3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622250"
---
### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a>RSACng e DSACng possono essere di nuovo usati in scenari di attendibilità parziale

#### <a name="details"></a>Dettagli

In alcuni casi, CngLightup (usato in diverse API di crittografia di livello superiore, ad esempio <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) e <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> si basano sull'attendibilità totale. Questi casi includono i P/Invoke senza l'asserzione delle autorizzazioni <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> e i percorsi di codice in cui <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> include richieste di autorizzazione per <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>. A partire da .NET Framework 4.6.2, CngLightup viene usato per passare a <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType>, quando possibile. Di conseguenza, le app con attendibilità parziale che usano <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> hanno iniziato a restituire errori e a generare eccezioni <xref:System.Security.SecurityException>. Questa modifica aggiunge le asserzioni necessarie in modo che tutte le funzioni che usano CngLightup abbiano le autorizzazioni richieste.

#### <a name="suggestion"></a>Suggerimento

Se questa modifica apportata in .NET Framework 4.6.2 ha avuto un impatto negativo sulle app con attendibilità parziale, eseguire l'aggiornamento a .NET Framework 4.7.1.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.6.2|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Security.Cryptography.DSACng.%23ctor(System.Security.Cryptography.CngKey)></li><li><xref:System.Security.Cryptography.DSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.LegalKeySizes?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.%23ctor(System.Security.Cryptography.CngKey)></li><li><xref:System.Security.Cryptography.RSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
